# Arquitetura prevista do SnowOS

**Estado:** proposta de organização, ainda não implementada/testada.

## Fluxo previsto

```text
Inicialização
  ├─ pilha e estado global
  ├─ endereços dos periféricos (a confirmar no circuito .cir)
  └─ carregamento da cena inicial
            ↓
Ciclo principal
  ├─ ler teclado matricial 4x4
  ├─ tratar comando / transição de cena
  ├─ atualizar neve (se não estiver pausada)
  ├─ atualizar acumulação e limpeza
  ├─ redesenhar os objetos alterados
  └─ repetir
```

## Blocos de código previstos

- **Constantes:** MediaCenter, teclado, estados das cenas, cores e dimensões.
- **Dados:** cena atual, velocidade, pausa, som, flocos e superfícies de acumulação.
- **Inicialização:** preparar periféricos e primeira cena.
- **Rotinas de desenho:** sprites, remoção, redesenho e composição.
- **Animação da neve:** posições dos flocos, movimento vertical, possível vento e limites do ecrã.
- **Acumulação:** estado visual separado do fundo, para permitir limpar a neve.
- **Entrada:** varrimento das quatro linhas e descodificação das 16 teclas.
- **Controlador:** eventos e funcionalidades do painel.
- **Áudio:** efeitos sonoros disponíveis no circuito e MediaCenter.

## Decisões técnicas pendentes

1. Ler o guião do MediaCenter e confirmar endereços e comandos reais.
2. Abrir o circuito antigo no SIMAC 2.3.0; verificar compatibilidade.
3. Confirmar que camadas e sprites são possíveis no circuito utilizado.
4. Definir a resolução e os sprites: ecrã padrão de **32 × 64 pixels**.
5. Testar uma estratégia barata de acumulação de neve (por exemplo alturas por coluna), sem redesenho desnecessário.
6. Definir temporização consistente para a animação, respeitando o âmbito da v2.
7. Decidir se o cursor é apenas decorativo ou controlado por teclas; não presumir entrada de rato no PEPE.

## Convenção de nomes (proposta)

- Constantes com `EQU` em maiúsculas: `CENA_DESKTOP`, `ESTADO_PAUSA`.
- Variáveis e etiquetas com nomes descritivos: `cena_atual`, `atualiza_neve`.
- Rotinas com uma responsabilidade; registar entradas, saídas e registos alterados.
- Comentários a explicar a *intenção*, não apenas a tradução da instrução.

**Nota:** não copiar automaticamente as rotinas do ano passado para `src/main.asm`. Primeiro auditar sintaxe, posições e dependência do circuito.
