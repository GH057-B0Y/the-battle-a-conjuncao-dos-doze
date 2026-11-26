# The Battle — A Conjunção Dos Doze (v5.2)

RPG de fantasia em Python com interface gráfica (Tkinter), pixel art procedural e trilha sonora adaptativa.

---

## Como Executar

1. **Extração:** Extraia todo o conteúdo do `.zip` em uma nova pasta (mantenha a pasta `artes/` e demais arquivos juntos).
2. **Jogar:**
   - **Windows:** Dê dois cliques em `JOGAR.pyw`.
   - **Terminal / Linux:** Execute `python main.py` dentro da pasta do projeto.
   - *Requisitos:* Python 3 com Tkinter (sem dependências externas obrigatórias para jogar).
3. **Trilha Sonora (Opcional):**
   - O jogo já acompanha arquivos `.wav` provisórios.
   - Para baixar as 9 faixas oficiais e habilitar controle de volume/MP3, execute `BAIXAR_BGM.bat` (instala `pygame` e baixa as músicas do Incompetech). Consulte `CREDITOS_MUSICA.md` caso precise baixar manualmente.
4. **Gerar Executável (Opcional):**
   - Execute `GERAR_EXE.bat` para instalar o `PyInstaller` e compilar o `.exe` sem console.

---

## Funcionalidades Principais

- **Mundo e Progressão:** 12 distritos inspirados no Zodíaco, 24 mercados com estoques diários, 24 encontros aleatórios e sistema manual de distribuição de pontos de atributo (`Vitalidade`, `Força`, `Defesa`, `Agilidade`).
- **Companhia e Vínculos:** Recrute até 3 aliados simultâneos (Ione, Raska, Vesper e Maelis) para sua equipe. Cada aliado possui afinidade própria (0–100), missões pessoais em 3 etapas, diálogos de grupo entre pares e habilidades de apoio gratuito em combate (1x por luta, sem gastar turno).
- **Masmorras e Revanches:** 12 masmorras opcionais de 10 ondas (9 inimigos + 1 chefe exclusivo). Após conquistar uma masmorra, é possível jogar revanches de 10 ondas para buscar novos equipamentos.
- **Relíquias do Zodíaco:** 12 equipamentos raros e 12 artefatos lendários equipáveis por qualquer classe (1 raro + 1 lendário simultaneamente), concedendo poderes ativos de uso único por combate sem gastar turno.
- **Áudio Adaptativo:** Trilhas dinâmicas para menu, exploração, viagem, mercado, diálogo, masmorra, combate, chefe e vitória, com botão de mudo na interface.

---

## Salvamento e Logs

- **Arquivo de Save:** `%USERPROFILE%\.the_battle\campanha.json` (ou `~/.the_battle/campanha.json`).
- **Compatibilidade:** Saves das versões **v1 a v4** são migrados automaticamente. Faça backup antes de atualizar, pois saves da **v5** não são retrocompatíveis.
- **Checkpoints:** Derrotas, retiradas ou fechamento do jogo durante combates restauram o estado (HP, MP, itens e ficha) do início do confronto/onda atual.
- **Registro de Erros:** Falhas inesperadas são registradas em `%USERPROFILE%\.the_battle\erros.log`.

---

## Estrutura do Projeto

- `main.py` / `JOGAR.pyw`: Pontos de entrada do jogo.
- `rpg.py`: Interface principal em Tkinter.
- `campanha.py`, `progressao.py`, `expansao.py`, `mundo.py`: Motores base, lore, eventos e progressão.
- `companheiros.py`, `equipe.py`: Sistema de aliados, afinidade, missões pessoais e diálogos de grupo.
- `masmorras.py`, `reliquias.py`: Ondas de masmorra, chefes, drops e poderes de relíquias.
- `audio.py`, `baixar_bgm.py`, `gerar_bgm.py`: Gerenciamento e instalação de trilha sonora.
- `personagem.py`, `dado.py`, `interface.py`: Módulos originais preservados (incluindo duelo local).
- `gerar_artes.py`, `gerar_masmorras.py`: Scripts opcionais (requerem `Pillow`) para recriar os 374 assets PNG da pasta `artes/`.

---

## Histórico Recente e Testes

- **v5.2:** Ajuste de janela e rolagem para monitores menores (ex.: `1366×768` e `1280×720`), gravação segura de campanha e log de erros sem terminal.
- **v5.1:** Inicializador Windows sem console persistente.
- **v5.0:** Adição de 24 relíquias, sistema de drops, revanches de masmorra e BGM adaptativa.
- **Testes:** Execute `python -m unittest discover -v` para rodar a suíte automatizada (32 testes cobrindo criação de personagem, rotas de missões, transições de masmorra, relíquias e migração de saves).
