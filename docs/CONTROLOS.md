# Controlos do teclado — proposta v2

O teclado do projeto é uma matriz **4 × 4**, com teclas **0–9 e A–F**. A implementação deve identificar corretamente cada tecla, por varrimento das quatro linhas.

| Tecla | Ação prevista |
| --- | --- |
| 0 | Mostrar desktop (cena 0) |
| 1 | Pausar / retomar queda de neve |
| 2 | Limpar neve acumulada |
| 3 | Ativar / desativar efeitos sonoros |
| 4 | Alternar velocidade lenta / normal / rápida |
| 5 | Abrir painel (cena 1) |
| 6 | Fechar painel / voltar ao desktop |
| 7 | Aumentar intensidade de neve |
| 8 | Diminuir intensidade de neve |
| 9 | Repor animação |
| A | Selecionar item anterior no painel |
| B | Selecionar item seguinte no painel |
| C | Confirmar seleção |
| D | Ativar / desativar neve |
| E | Efeito sonoro festivo |
| F | Ajuda / indicação de teclas |

**Isto é um mapa proposto, não código implementado.** Ajustar depois de testar a ergonomia no MediaCenter. Para a v2, garantir 16 teclas com comportamentos definidos e pelo menos seis comandos de animação ou som.

## Casos de teste previstos

- [ ] Cada uma das 16 teclas é detetada com a codificação correta.
- [ ] Uma tecla pressionada uma vez não produz ativações repetidas indesejadas.
- [ ] Pausar bloqueia a atualização dos flocos; retomar continua.
- [ ] Limpar neve remove acumulação sem apagar o fundo.
- [ ] Mudança de velocidade altera a animação e respeita limites.
- [ ] Áudio é ativado/desativado e som festivo é reproduzido.
- [ ] Trocar de cena mantém estado coerente.
- [ ] Regressar ao desktop funciona independentemente do estado de pausa.

**Interação com rato:** a captura/simulação do desktop apresenta cursor, mas o projeto do professor é controlado por teclado. Um cursor pode ser desenhado, não equivale à leitura do rato do Windows.
