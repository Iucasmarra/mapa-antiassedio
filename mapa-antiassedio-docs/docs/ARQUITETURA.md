# Arquitetura Técnica

## Visão geral

O Mapa Antiassédio é estruturado como uma aplicação mobile-first com três camadas principais: frontend colaborativo, backend de dados e motor de inteligência artificial.

```
┌─────────────────────────────────────────┐
│              FRONTEND (App)             │
│  Mapa · Registro · Astra IA · SOS      │
└────────────────┬────────────────────────┘
                 │
┌────────────────▼────────────────────────┐
│              BACKEND / API              │
│  Node.js · REST · Auth · Notificações  │
└────────────────┬────────────────────────┘
                 │
┌────────────────▼────────────────────────┐
│           CAMADAS DE IA                 │
│  NLP · ML Preditivo · Edge AI · Mod.   │
└─────────────────────────────────────────┘
```

---

## Frontend

Tecnologia atual do protótipo: HTML5 + CSS3 + JavaScript vanilla (single-file).

Tecnologia prevista para produção: React Native (Android e iOS nativos).

Principais telas:

| Tela | Função |
|---|---|
| Autenticação | Login, cadastro, configuração de contatos de emergência |
| Mapa | Heatmap de ocorrências, filtros, navegação |
| Registro | Formulário de ocorrência com geolocalização |
| Astra IA | Chat com IA de acolhimento |
| Perfil | Histórico, conquistas, configurações, contatos |

---

## Backend (roadmap)

```
Tecnologia prevista: Node.js + Express
Banco de dados: PostgreSQL (dados estruturados) + Redis (cache/realtime)
Autenticação: JWT com refresh token
Notificações: Firebase Cloud Messaging (push)
Armazenamento: AWS S3 (mídias opcionais)
```

Endpoints principais previstos:

```
POST /auth/register
POST /auth/login
GET  /occurrences?lat=&lng=&radius=&type=&period=
POST /occurrences
GET  /occurrences/:id
PUT  /user/contacts
POST /sos/trigger
```

---

## Camadas de IA

### 1. NLP — Astra (Chatbot de acolhimento)

```
Entrada:  texto ou áudio da usuária
Modelo:   LLM via API (GPT-4 / Claude)
Saída:    JSON com { local, tipo, urgencia, mensagem_apoio }
```

System Prompt base:

```
PAPEL: Você é Astra, assistente empática do Mapa Antiassédio. Nunca julgue.

TAREFA: Extraia do relato da usuária:
- local (rua / estação / bairro)
- tipo_ocorrencia (verbal, físico, perseguição, outro)
- nivel_urgencia (baixo / médio / alto)

RESPONDA SOMENTE em JSON:
{
  "local": "...",
  "tipo": "...",
  "urgencia": "...",
  "mensagem_apoio": "..."
}
```

### 2. ML — Mapa de calor preditivo

```
Biblioteca: scikit-learn (Python)
Modelo:     Gradient Boosting por região
Entrada:    histórico de ocorrências + horário + iluminação + fluxo estimado
Saída:      score de risco 0–100 por quadrante, atualizado a cada hora
```

### 3. Edge AI — Acionamento por voz

```
Modelo:   TensorFlow Lite embarcado no dispositivo
Função:   reconhecimento de palavras-chave de socorro
Trigger:  aciona SOS sem tocar na tela
Offline:  funciona sem internet
```

### 4. Agente de moderação

```
Modelo:     Isolation Forest (sklearn)
Função:     detectar padrões anômalos (ex: conta nova + muitos registros distantes em < 1 min)
Ação:       quarentena automática até validação cruzada com GPS
```

---

## Fluxo de dados — Registro de ocorrência

```
Usuária relata → Astra extrai entidades → Backend valida
       ↓
Agente de moderação analisa padrão
       ↓
[SUSPEITO] → Quarentena   [OK] → Mapa atualizado
                                        ↓
                            Outros usuários notificados
```

---

## Privacidade e segurança

- Todos os dados são anonimizados antes do processamento
- Consentimento explícito via opt-in (LGPD)
- Criptografia end-to-end no envio
- Dados sensíveis nunca exibidos individualmente no mapa
- Apenas padrões agregados são expostos publicamente
- Política clara de retenção e exclusão de dados
