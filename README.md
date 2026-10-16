# 🛡️ Mapa Antiassédio

> Uma rede colaborativa de proteção urbana com Inteligência Artificial.

[![Status](https://img.shields.io/badge/status-protótipo%20ativo-E8628A?style=flat-square)](https://claude.ai/artifact/QmpH67BT9kzRBGpV9njjGb)
[![Licença](https://img.shields.io/badge/licença-MIT-0D2137?style=flat-square)](LICENSE)
[![Feito com](https://img.shields.io/badge/feito%20com-HTML%20%2B%20CSS%20%2B%20JS-133052?style=flat-square)](#tecnologias)

---

## Sobre o projeto

O **Mapa Antiassédio** é um aplicativo mobile colaborativo que permite registrar, visualizar e prevenir situações de assédio em espaços públicos. A solução utiliza geolocalização, dados fornecidos pela comunidade e Inteligência Artificial para aumentar a segurança urbana e permitir que as pessoas tomem decisões mais seguras em seus deslocamentos.

Mais do que um aplicativo, o Mapa Antiassédio propõe uma **rede de proteção baseada na colaboração**, na informação e no uso inteligente da tecnologia para promover bem-estar e autonomia no dia a dia.

---

## Demonstração

**Protótipo interativo:** [claude.ai/artifact/QmpH67BT9kzRBGpV9njjGb](https://claude.ai/artifact/QmpH67BT9kzRBGpV9njjGb)

> Para testar sem conta no Claude, faça o deploy do arquivo `index.html` no [Netlify Drop](https://app.netlify.com/drop) arrastando o arquivo para a página.

---

## Funcionalidades

**Mapa de risco**
- Heatmap interativo com áreas de maior incidência de ocorrências
- Filtros por tipo de ocorrência (assédio verbal, perseguição, físico, iluminação)
- Arrastar e navegar pelo mapa livremente
- Contadores de alertas atualizados em tempo real conforme filtros

**Registro de ocorrências**
- Seleção de tipo e nível de urgência
- Geolocalização automática
- Opção de denúncia anônima
- Descrição livre em texto

**Astra IA**
- Chatbot de acolhimento empático alimentado por LLM
- Extrai automaticamente local, tipo de ocorrência e urgência do relato
- Oferece orientações legais e suporte psicológico inicial
- Respostas em linguagem natural, sem julgamentos

**Botão SOS**
- Acionamento com um toque
- Notifica contatos de emergência cadastrados com localização em tempo real
- Aciona automaticamente a Polícia Militar, Central 190 e CISP da região

**Perfil e configurações**
- Histórico completo de registros
- Conquistas e gamificação (selos)
- Configurações de privacidade e notificações
- Gerenciamento de contatos de emergência (adicionar, editar, excluir)

**Cadastro e autenticação**
- Fluxo de criação de conta com senha
- Configuração de até 3 contatos de emergência no onboarding

---

## Tecnologias

| Camada | Tecnologia |
|---|---|
| Frontend | HTML5, CSS3, JavaScript (vanilla) |
| Tipografia | Inter, DM Sans (Google Fonts) |
| IA conversacional | LLM via API (Astra) |
| IA preditiva (roadmap) | scikit-learn, Gradient Boosting |
| Moderação (roadmap) | Isolation Forest (sklearn) |
| Edge AI (roadmap) | TensorFlow Lite embarcado |
| Mapas (roadmap) | Google Maps API |
| Backend (roadmap) | Node.js, banco de dados em nuvem |

---

## Inteligência Artificial no projeto

O projeto utiliza três camadas de IA integradas:

**1. NLP — Astra (Chatbot de acolhimento)**
Processa linguagem natural para extrair entidades do relato da vítima (local, tipo, horário) e preenche o registro automaticamente, além de oferecer suporte psicológico inicial.

**2. ML — Análise preditiva**
Modelos de Machine Learning cruzam o histórico de ocorrências com variáveis externas (horário, iluminação, fluxo de pessoas) para gerar mapas de calor preditivos e sugerir rotas mais seguras.

**3. Edge AI — Emergência por voz**
Modelo TFLite embarcado no dispositivo reconhece palavras-chave de socorro configuradas pela usuária e aciona o SOS automaticamente, sem necessidade de tocar na tela.

**4. Agente de moderação**
Modelo de detecção de anomalias (Isolation Forest) analisa padrões de comportamento para identificar denúncias falsas e enviá-las para quarentena antes de aparecerem no mapa.

---

## Como usar o protótipo localmente

```bash
# Clone o repositório
git clone https://github.com/sehrbaz/mapa-antiassedio.git

# Abra o arquivo diretamente no navegador
open index.html
```

Não há dependências externas. O protótipo funciona 100% offline, exceto pela integração com a Astra IA (requer conexão e conta Claude).

---

## Estrutura do projeto

```
mapa-antiassedio/
├── index.html          # Protótipo completo (single-file)
├── README.md           # Este arquivo
├── CONTRIBUTING.md     # Guia de contribuição
├── LICENSE             # Licença MIT
└── docs/
    ├── ARQUITETURA.md  # Arquitetura técnica detalhada
    └── ROADMAP.md      # Próximos passos e versões
```

---

## ODS relacionados

| ODS | Descrição |
|---|---|
| 5 — Igualdade de Gênero | Combate ao assédio e empoderamento de mulheres em espaços urbanos |
| 11 — Cidades Sustentáveis | Cidades mais seguras, inclusivas e com mobilidade protegida |
| 16 — Paz e Justiça | Incentivo à denúncia, transparência e fortalecimento das instituições |

---

## Stakeholders

- Usuárias principais: mulheres em espaços urbanos
- Usuários colaboradores: qualquer pessoa que registre ocorrências
- Governo e prefeituras: uso dos dados agregados para políticas públicas
- ONGs: parceiras na tração e validação
- Polícia e segurança pública: uso indireto dos dados

---

## Autor

**Lucas Carvalho Neves Oliveira**
Engenharia de Prompt — 2026.2
GitHub: [@sehrbaz](https://github.com/sehrbaz)

---

## Licença

Distribuído sob a licença MIT. Veja [LICENSE](LICENSE) para mais informações.
