# ❄️ SnowOS — Vitrine Natalícia no SIMAC

![Estado](https://img.shields.io/badge/estado-em%20desenvolvimento-blue)
![Assembly](https://img.shields.io/badge/linguagem-PEPE--16%20Assembly-informational)
![Simulador](https://img.shields.io/badge/SIMAC-2.3.0-informational)

**Projeto Final de Arquitetura de Computadores · LESTI · Universidade do Algarve · 2026/2027**

O **SnowOS** é uma vitrine natalícia com aspeto de um pequeno sistema operativo: um **desktop de inverno em Pixel Art**, com neve a cair e a acumular-se sobre elementos da interface. Uma aplicação fictícia, **Controlo da Neve**, abre um painel para o utilizador interagir com a animação.

> **Estado:** estrutura inicial de desenvolvimento. As funcionalidades descritas são objetivos, não funcionalidades já implementadas ou testadas.

## 🎯 Objetivo académico

Desenvolver em **Assembly do PEPE-16**, no **SIMAC 2.3.0**, uma vitrine festiva com duas cenas, animações, teclado de 16 teclas, efeitos sonoros e rotinas organizadas. A meta é a **versão v2** do enunciado de 2026/27, com **14 valores indicativos para Material Prático (MP)** — não uma nota final garantida.

A nota final do projeto é `NF = min(MP, AO, RT)`, em que AO é apresentação oral e RT é relatório técnico (até 6 páginas). A demonstração e a capacidade de explicar o código são essenciais.

## 🖥️ Conceito visual

| Cena | Descrição |
| --- | --- |
| **0 — Desktop de inverno** | Fundo de montanhas e céu de inverno; ícones em Pixel Art; neve a cair, com possível acumulação e limpeza visual. |
| **1 — Controlo da Neve** | Composição/painel de controlo da animação, **com fundo próprio** e efeitos sonoros adequados. |

No painel, estão previstas quatro funções:

1. **Pausar/retomar a neve**
2. **Limpar toda a neve**
3. **Ativar/desativar o som**
4. **Mudar a velocidade da neve**

Para cumprir a v2, **não bastam quatro funções**: será necessário implementar leitura de **todas as 16 teclas (0–F)** e utilizar **pelo menos 6 teclas distintas** para animações e/ou sons. O mapeamento final está em [docs/CONTROLOS.md](docs/CONTROLOS.md).

**Importante:** o rato do Windows não é um periférico de entrada previsto para este projeto. A interação real da entrega será feita pelo **teclado do SIMAC**; um cursor desenhado no MediaCenter pode simular a experiência de “clicar” e “limpar”. Uma aplicação que adicione neve ao desktop real do Windows seria outro projeto.

## 🧱 Estrutura do repositório

```text
vitrinedenatal_SIMAC/
├── README.md
├── .gitignore
├── src/
│   └── main.asm                  # ponto de partida (ainda sem animação)
├── circuit/
│   └── .gitkeep                 # circuito SIMAC .cir final, quando validado
├── assets/
│   ├── backgrounds/.gitkeep     # imagens de fundo das duas cenas
│   ├── sprites/.gitkeep         # fontes PNG e sprites em Pixel Art
│   └── sounds/.gitkeep          # pequenos sons festivos
├── docs/
│   ├── ARQUITETURA.md           # organização do programa e decisões
│   ├── CONTROLOS.md            # mapa das teclas e comportamento
│   └── CHECKLIST.md            # acompanhamento dos requisitos v2
└── legacy/
    └── README.md               # inventário dos ficheiros do ano passado
```

O **circuito `.cir` e os assets multimédia devem ficar na mesma pasta ou em subpastas com caminhos relativos**. Quando o circuito real for criado, confirmar no SIMAC a forma de referenciar os ficheiros. Não usar caminhos absolutos do computador.

## ▶️ Como executar (quando o circuito estiver pronto)

1. Instalar/abrir o **SIMAC 2.3.0**, disponibilizado na Tutoria.
2. Clonar ou descarregar este repositório.
3. Abrir o ficheiro `.cir` definitivo da pasta `circuit/` no SIMAC.
4. Entrar em **Simulation**, abrir o PEPE-16 e carregar o programa `.asm` da pasta `src/` (ou utilizar o programa associado ao circuito depois de o guardar).
5. Iniciar a simulação e testar as teclas e as duas cenas.

> **Ainda não existe um circuito final publicado neste repositório.** Os passos acima são o procedimento previsto, e serão revistos após validação no simulador.

## 📌 Plano de desenvolvimento

- [ ] Importar uma **cópia de referência** do projeto 2025/26 para `legacy/`, depois de rever código, ficheiros e autoria.
- [ ] Testar a rotina de desenho de sprites e a animação de neve do projeto anterior.
- [ ] Desenhar o desktop e quatro ou mais objetos em Pixel Art no MediaCenter (mínimo padrão: 32 linhas × 64 colunas).
- [ ] Implementar neve a cair, acumulação e limpeza visual.
- [ ] Implementar varrimento do teclado matricial (0–F) e pelo menos seis controlos úteis.
- [ ] Implementar a segunda cena com imagem de fundo distinta.
- [ ] Integrar efeitos sonoros e comandos do painel.
- [ ] Organizar rotinas, comentários, dados e temporização; testar limites do ecrã.
- [ ] Testar todos os caminhos relativos, preparar demonstração e concluir relatório técnico.

Detalhes em [docs/CHECKLIST.md](docs/CHECKLIST.md).

## ♻️ Código anterior

O projeto de 2025/26 é uma **referência para reaproveitamento e refatoração**, não uma entrega final pronta. Os ficheiros existentes são listados em [legacy/README.md](legacy/README.md). Serão importados apenas após revisão e mantidos separados do código novo.

## 📚 Documentação

- [Arquitetura e decisões técnicas](docs/ARQUITETURA.md)
- [Controlos do teclado](docs/CONTROLOS.md)
- [Checklist de avaliação e testes](docs/CHECKLIST.md)
- [Página de planeamento no Notion](https://app.notion.com/p/40445f7810cd81368ea5ef2ba102e8c2)

## 📷 Demonstração

Screenshots e vídeo serão adicionados **apenas quando houver uma versão funcional no SIMAC**. Os mockups conceptuais das duas cenas não representam screenshots da execução real.

---

Desenvolvido como projeto académico de Arquitetura de Computadores. O enunciado e materiais do docente não são redistribuídos neste repositório. Verificar sempre a autoria e as licenças antes de publicar imagens, sons ou código de terceiros.
