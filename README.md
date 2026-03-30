### Validação da Parte 4 – Paralelismo (Job 2 e Job 3)

Com base na execução do pipeline no ambiente local:

- Os jobs `testes-unitarios` (Job 2) e `scan-de-seguranca` (Job 3) aparecem na mesma Stage 1 quando listados com `act -l`.
- Durante a execução completa (`act -W 02-pipeline-principal.yml`), os logs de ambos aparecem intercalados:
  [testes-unitarios] Rodando testes unitários...
  [scan-de-seguranca] Procurando vulnerabilidades...
  [testes-unitarios] Testes finalizados
  [scan-de-seguranca] Scan finalizado
- Isso mostra que os dois jobs foram executados simultaneamente em contêineres separados, ou seja, em paralelo, sem depender um do outro.
