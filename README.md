# Projeto de Computação Gráfica

Este documento descreve o funcionamento, organização e principais componentes do projeto em HTML/JavaScript que implementa:

* Curvas paramétricas 2D/3D
* Splines e Bézier
* Superfícies de revolução
* Sistema de câmera e iluminação
* Animação do personagem **Alus** com trajetória em espiral Fibonacci (Golden Spiral)
* Visualização interativa usando **Three.js**

---

## 📌 Estrutura Geral do Projeto

O projeto está contido em um único arquivo HTML que integra:

* **HTML**: Interface básica e controles do usuário.
* **CSS**: Estilização dos componentes visuais.
* **JavaScript (Three.js)**: Renderização 3D, curvas, superfícies e animações.

O código é totalmente autônomo, bastando abrir o arquivo `aplicação.html` no navegador.

---

## 🌀 Módulo: Voo do Alus (Espiral Fibonacci)

A trajetória do Alus foi corrigida para seguir uma **espiral dourada autêntica**, usando a razão áurea:

[
r = a \cdot \varphi^{t}
]

No código:

* A espiral cresce suavemente baseado na **razão áurea (PHI ≈ 1.618)**.
* O ângulo avança em passos proporcionais a 1/φ.
* A altura segue um movimento suave de subida e descida.
* Pontos são conectados usando **Catmull-Rom spline** com suavização.

O resultado é um voo orgânico, contínuo e natural.

---

## 🔧 Módulo: Superfície de Revolução

O sistema de revolução:

* Permite criar objetos 3D girando um perfil em torno de um eixo.
* Usa `LatheGeometry` do Three.js.
* Permite controlar quantidade de segmentos e forma do perfil.

É utilizado para visualização e testes em Computação Gráfica.

---

## ✏️ Módulo: Curvas Bézier e Splines

O projeto inclui:

### ✔ Bézier cúbica

Implementada com:

* `QuadraticBezierCurve3`
* Controle visual dos pontos

### ✔ Catmull-Rom Spline

* Suavização ajustável
* Perfeita para trajetórias animadas (como o Alus)

---

## 🎥 Câmera e Animação

O ambiente possui:

### Câmera

* `PerspectiveCamera`
* Controle orbital (`OrbitControls`)
* Zoom, pan e rotação

### Animação

* `requestAnimationFrame`
* Movimento do Alus ao longo da curva
* Atualização contínua de posição e orientação

---

## 📁 Estrutura Recomendada de Arquivos

Se quiser separar o projeto:

```
aplicação.html
js/
  ├─ curvas.js
  ├─ alus.js
  ├─ revolucao.js
  ├─ cenas.js
css/
  └─ estilo.css
```

---

## ▶️ Como Executar

1. Abra `aplicação.html` em qualquer navegador moderno.
2. Navegue entre as guias para visualizar:

   * Curvas Bézier
   * Splines
   * Superfícies de Revolução
   * Animação do Alus (Fibonacci)

Nenhuma instalação é necessária.

---

## 🚀 Melhorias Futuras

Se desejar, posso adicionar:

* Exportação OBJ/GLTF
* Modo VR
* Sistema de colisão e física simples
* Interface renovada com sliders
* Sombras e materiais realistas
