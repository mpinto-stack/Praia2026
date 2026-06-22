# Tutorial para meter em GitHub — V4 corrigida

## Estrutura final
```text
Praias_VF_V4_fix/
  index.html
  .nojekyll
  logo_site.png
  verify_v4.js
  service-worker.js
  manifest.webmanifest
  icons/
    icon-192.png
    icon-512.png
  scripts/
    update_data.py
  data/
    beaches_source.json
    meta.json
    weather_snapshot.json
    weather_forecast_3d.json
    update_history.json
    ipma/
      sea_day0.json
      sea_day1.json
      sea_day2.json
      sea_locations.json
      warnings.json
  .github/
    workflows/
      update_site_data.yml
```

## Passos
1. Faz download do ZIP desta correção.
2. Descompacta no computador.
3. Substitui os ficheiros existentes do repositório pelos ficheiros desta pasta.
4. Confirma que a pasta do script se chama exatamente `scripts/`.
5. Faz commit e push.
6. Vai a **GitHub > Actions**.
7. Corre manualmente a workflow **Update sea and weather data** uma vez.
8. Depois confirma no repositório:
   - `data/meta.json` sem `null`
   - `data/weather_snapshot.json` com entradas
   - `data/weather_forecast_3d.json` com previsão de 3 dias
   - `data/update_history.json` com histórico
   - `data/ipma/sea_day0.json`, `sea_day1.json`, `sea_day2.json` com conteúdo

## Validação no site
- semáforo do topo deixa de estar em estado antigo/sem update depois da primeira workflow bem-sucedida
- briefing do dia aparece
- comparação temporal aparece
- detalhe da praia mostra previsão 3 dias
- comparador funciona
- botão “Exportar resumo” gera ficheiro `.md`

## Atualização mínima de 4 em 4 horas
- O cron da workflow é `15 */4 * * *`.
- GitHub Actions usa UTC.
- Isto garante tentativa automática de atualização a cada 4 horas.
