# Cofre Inteligente com Arduino

## Componentes Utilizados

- 1x Arduino Uno
- 1x Display LCD 16x2
- 1x Servo Motor
- 1x Sensor de temperatura TMP36 (durante a apresentação utilizamos outro, pois nao tinha. "DTH11")
- 1x Buzzer
- 1x LED
- 4x Botões
- Resistores
- Protoboard
- Jumpers

---

# Funcionamento do Sistema

## Inicialização

Ao ligar o Arduino:

- O display LCD mostra:

```txt
Digite senha:
```

- O servo motor permanece na posição de fechado;
- O LED permanece ligado indicando sistema ativo;
- O sistema aguarda entrada da senha.

---

# Sistema de Senha

A senha definida no código é:

```txt
123412
```

---

## LCD

Exibe:

```txt
Senha Correta
Cofre Aberto
```

## Servo Motor

O servo gira de:

```txt
0° → 90°
```

Simulando a abertura do cofre.

## LED

O LED é desligado indicando cofre aberto.

## Buzzer

O buzzer toca uma sequência sonora crescente:

- 1000 Hz
- 1500 Hz
- 2000 Hz

Indicando sucesso na autenticação.

---

# Senha Incorreta

Caso a senha esteja errada:

## LCD

Exibe:

```txt
Senha Errada
```

## Buzzer

Emite um tom grave:

```txt
300 Hz
```

Durante aproximadamente 700 ms.

Após isso o sistema reinicia a entrada da senha.

---

# Sistema de Incêndio

O projeto possui suporte para detecção de incêndio utilizando o sensor TMP36.

A função:

```cpp
verificarIncendio();
```

---

## Funcionamento do Sensor

O sensor lê a temperatura através da porta analógica A1.

Quando a temperatura ultrapassa:

```txt
50°C
```

o sistema entra em modo de emergência.

---

# Modo Emergência

Quando incêndio é detectado:

## Servo

O cofre é automaticamente fechado.

## LCD

Exibe:

```txt
Incendio
detectado!
```

## LED

O LED começa a piscar continuamente.

## Buzzer

O buzzer toca alarmes repetitivos em:

```txt
2500 Hz
```

Até a temperatura voltar ao normal.

---

# Funções do Projeto

| Função | Responsabilidade |
|---|---|
| `mostrarTelaInicial()` | Mostra tela padrão |
| `verificarBotao()` | Detecta botão pressionado |
| `verificarSenha()` | Valida senha |
| `abrirCofre()` | Abre o cofre |
| `senhaErrada()` | Trata erro de autenticação |
| `verificarIncendio()` | Detecta altas temperaturas |

---


# Autor

Projeto desenvolvido para fins educacionais utilizando Arduino e Tinkercad.
