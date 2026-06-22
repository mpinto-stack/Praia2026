# Praia2026

Site para apoiar a escolha da melhor praia durante as férias, com foco em simplicidade, comparação rápida e apoio à decisão em família.

## O que o site faz
- Mostra um **briefing do dia** com as melhores opções.
- Calcula um estado **Go / Maybe / No-Go** para cada praia.
- Permite comparar **Hoje / Amanhã / Daqui a 2 dias**.
- Filtra por vento, temperatura do ar, temperatura da água, tempo de carro e tipo de praia.
- Tem modos rápidos como **Família**, **Dia fácil**, **Sossego**, **Mais perto** e **Mar/ondas**.
- Permite guardar favoritas, comparar até 3 praias e exportar um resumo em Markdown.
- Funciona como **PWA** e tem suporte parcial a **offline**.

## Dados usados
O site combina:
- dados locais curados em `data/beaches_source.json`
- previsão e snapshot de tempo via **Open-Meteo**
- dados do mar, avisos e localizações costeiras via **IPMA**

## Atualização automática
Os ficheiros de dados são atualizados automaticamente por GitHub Actions através do script:
- `scripts/update_data.py`

A workflow está em:
- `.github/workflows/update_site_data.yml`

## Estrutura principal
- `index.html` — interface principal
- `verify_v4.js` — lógica da aplicação
- `service-worker.js` — cache/offline
- `manifest.webmanifest` — configuração PWA
- `data/` — dados usados pelo site
- `scripts/update_data.py` — atualização automática

## Objetivo
Este projeto foi pensado para ajudar a escolher praia de forma rápida e prática, sem ter de abrir múltiplos sites de meteorologia, mar e mapas.

## Notas
- A app foi desenhada para uso familiar e consulta rápida em telemóvel.
- Se os dados ainda não tiverem sido atualizados, alguns painéis podem aparecer sem conteúdo até à próxima execução da workflow.
