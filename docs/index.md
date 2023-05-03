![logo do projeto](assets/logo.png){ width='300' .center}
# Notas musicais

Notas musicais é um CLI para ajudar na formaçao de escalas e acordes e
campos harmônicos

Toda a aplicação é baseada em um comando chamado `notas-musicais`. Esse
comando tem um subcomando relacionado a cada ação que a aplicação pode
realizar. Como `escalas`, `acordes` e `campo-harmonico`

Temos dois comandos disponíveis: `escala` e `acorde`

## como usar?

### Escalas

Você pode chamar as escalas via linha de comando. Por exemplo:

```bash
poetry run notas-musicais escala
```

Retornando os graus e as notas correspondentes a essa escala:
```
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━┓
┃ I ┃ II ┃ III ┃ IV ┃ V ┃ VI ┃ VII ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━┩
│ C │ D  │ E   │ F  │ G │ A  │ B   │
└───┴────┴─────┴────┴───┴────┴─────┘

```

#### Alteração da tônica da escala

O primeiro parâmetro do CLI é a tônica da escala que deseja exibir. Desta forma, 
você pode alterar a escala retornada. Por exemplo, a escala de `F#`

```bash
poetry run notas-musicais escala F#
```

Resultado em:
```
┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ F# │ G# │ A#  │ B  │ C# │ D# │ F   │
└────┴────┴─────┴────┴────┴────┴─────┘
```

#### Alteração na tonalidade da escala

Você pode alterar a tonalidade da escala também! Esse é o segundo parâmetro
da linha de comando. Por exemplo, a escala de `D#` menor

```
poetry run notas-musicais escala D# menor

┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ D# │ F  │ F#  │ G# │ A# │ B  │ C#  │
└────┴────┴─────┴────┴────┴────┴─────┘
```
## Acordes

Uso básico

```
poetry run notas-musicais acorde
┏━━━┳━━━━━┳━━━┓
┃ I ┃ III ┃ V ┃
┡━━━╇━━━━━╇━━━┩
│ C │ E   │ G │
└───┴─────┴───┘
```

### Variações na cifra

```
poetry run notas-musicais acorde C+
┏━━━┳━━━━━┳━━━━┓
┃ I ┃ III ┃ V+ ┃
┡━━━╇━━━━━╇━━━━┩
│ C │ E   │ G# │
└───┴─────┴────┘

```

Até o momento você pode usar acordes maiores, menores, diminuto e aumentados

## Campo harmônico

Você pode chamar os campos harmônicos via o subcomando `campo-harmonico`.
 Por exemplo:
```
poetry run notas-musicais campo-harmonico
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━━┓
┃ I ┃ ii ┃ iii ┃ IV ┃ V ┃ vi ┃ vii° ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━━┩
│ C │ Dm │ Em  │ F  │ G │ Am │ B°   │
└───┴────┴─────┴────┴───┴────┴──────┘
```

Por padrão os parâmetros utilizados são a tônica de `C` e o campo harmônico 
`maior`.

### Alterações nos campos harmônicos

Você pode alterar os parâmetros da tônica e da tonalidade.

```bash
notas-musicais campo-harmonico [OPTIONS] [TONICA] [TONALIDADE]  
```

#### Alteração na tônica do campo

Um exemplo com o campo harmônico de `E`:

```
poetry run notas-musicais campo-harmonico E
┏━━━┳━━━━━┳━━━━━┳━━━━┳━━━┳━━━━━┳━━━━━━┓
┃ I ┃ ii  ┃ iii ┃ IV ┃ V ┃ vi  ┃ vii° ┃
┡━━━╇━━━━━╇━━━━━╇━━━━╇━━━╇━━━━━╇━━━━━━┩
│ E │ F#m │ G#m │ A  │ B │ C#m │ D#°  │
└───┴─────┴─────┴────┴───┴─────┴──────┘
```

#### Alteração da tonalidade do campo

Um exemplo utilizando o campo harmônico de `E` na tonalidade `menor`:

```
poetry run notas-musicais campo-harmonico E menor
┏━━━━┳━━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ i  ┃ ii° ┃ III ┃ iv ┃ v  ┃ VI ┃ VII ┃
┡━━━━╇━━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ Em │ F#° │ G   │ Am │ Bm │ C  │ D   │
└────┴─────┴─────┴────┴────┴────┴─────┘
```

## Mais informações sobre o CLI

Para descobrir outras opções, você pode usar a flag `--help`:

```
poetry run notas-musicais --help

 Usage: notas-musicais [OPTIONS] COMMAND [ARGS]...    
                                                                                                              
╭─ Commands ────────────────────────────────────────────────────────────────╮
│ acorde                                                                    │
│ campo-harmonico                                                           │
│ escala                                                                    │
╰───────────────────────────────────────────────────────────────────────────╯
```

### Mais informações sobre os subcomandos

As informações sobre os subcomandos podem ser acessadas usando a flag `--help` após o 
nome do parâmetro. Um exemplo do uso do `help` nos campos harmônicos:

```
poetry run notas-musicais campo-harmonico --help
                                                                                                                
 Usage: notas-musicais campo-harmonico [OPTIONS] [TONICA] [TONALIDADE]                                          
                                                                                                                
╭─ Arguments ──────────────────────────────────────────────────────────────────────────────────────────────────╮
│   tonica          [TONICA]      Tônica do campo harmônico [default: c]                                       │
│   tonalidade      [TONALIDADE]  Tonalidade do campo harmônico [default: maior]                               │
╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --help          Show this message and exit.                                                                  │
╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
```