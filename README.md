# Digilog Clock

Uma implementacao experimental de relogio hibrido desenvolvida com HTML5 Canvas e JavaScript puro. O projeto combina conceitos visuais de relogios analogicos e digitais: os ponteiros convencionais sao substituidos por sequencias radiais repetidas dos proprios numerais correspondentes ao tempo corrente (horas, minutos e segundos).

## Demonstracao

O projeto esta configurado para execucao direta no navegador e compativel com GitHub Pages.

Acesse a demonstracao: https://elen.is-a.dev/analog-digital-canvas-clock/



https://github.com/user-attachments/assets/6690f2c4-d8f5-4cf2-8bcf-5a6b1afeacce



## Caracteristicas Tecnicas

* **Renderizacao em Canvas 2D:** Todo o desenho e atualizacao ocorrem via API de Canvas do HTML5 sem bibliotecas externas.
* **Calculo Trigonometrico:** Posicionamento e rotacao angular baseados em conversoes de graus para radianos (`Math.PI / 180`), incluindo compensacao continua do ponteiro de horas com base nos minutos decorridos.
* **Suporte a Alta Densidade de Pixels (HiDPI):** Buffer interno com resolucao de 880x880px redimensionado via CSS para garantir nitidez em telas Retina e 4K.
* **Design Responsivo:** Adaptacao de escala proporcional utilizando `min()`, `clamp()` e unidades de viewport dinamicas (`100dvh`).
* **Tipografia Monoespacada:** Formatacao com preenchimento de zeros a esquerda (`padStart`) e uso da fonte JetBrains Mono para prevenir variacoes de largura durante a atualizacao dos digitos.

## Estrutura do Codigo

O projeto e composto por um arquivo unico autocontido:

* `index.html`: Contem a estrutura semantica, estilos CSS (Dark Mode e efeitos visuais) e a logica do loop de renderizacao via `requestAnimationFrame`.

### Mapeamento de Ponteiros

| Unidade | Repeticoes | Escala de Fonte | Peso Visual | Compensacao Angular |
| :--- | :--- | :--- | :--- | :--- |
| **Horas** | 4 | 32px | 800 (Bold) | Sim (30°/h + 0.5°/min) |
| **Minutos** | 6 | 28px | 600 (Semi-bold) | Sim (6°/min + 0.1°/sec) |
| **Segundos** | 8 | 24px | 600 (Semi-bold) | Nao (6°/sec) |

## Como Executar Localmente

1. Clone este repositorio:
```bash
git clone https://github.com/elen-c-sales/analog-digital-canvas-clock.git
