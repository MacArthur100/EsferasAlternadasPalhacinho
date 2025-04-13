Exercício Prática de Desing 2º semestre Curso Sistemas para Internet - FATEC

Descrição do código

<!DOCTYPE html> // Declara que este é um documento HTML5
<html lang="pt-br"> // Início do documento HTML com idioma definido como português do Brasil
<head>
  <meta charset="UTF-8"> // Define a codificação de caracteres como UTF-8
  <title>Esferas Animadas</title> // Título da página que aparece na aba do navegador
  <style>
    body {
      margin: 0; // Remove margem padrão do body
      height: 100vh; // Altura total da janela do navegador (viewport height)
      background: #f0f0f0; // Cor de fundo cinza claro
      display: flex; // Usa Flexbox para centralizar o conteúdo
      justify-content: center; // Centraliza horizontalmente
      align-items: center; // Centraliza verticalmente
    }

    .container {
      position: relative; // Permite posicionar elementos filhos de forma absoluta
      width: 300px; // Largura do container
      height: 300px; // Altura do container
    }

    .person {
      position: absolute; // Posicionamento absoluto dentro do container
      top: 50%; // Move 50% do topo do container
      left: 50%; // Move 50% da esquerda do container
      transform: translate(-50%, -50%); // Centraliza a imagem exatamente no centro
      width: 120px; // Largura da imagem
      height: 120px; // Altura da imagem
      border-radius: 50%; // Deixa a imagem circular
      background-image: url('clown-1295519_1280.png'); // Caminho da imagem de fundo
      background-size: cover; // Cobre todo o espaço disponível
      background-position: center; // Centraliza a imagem dentro do círculo
      z-index: 2; // Fica acima das esferas

      animation: move-side 2s infinite ease-in-out; // Aplica a animação lateral de forma infinita
    }

    .sphere {
      position: absolute; // Posicionamento absoluto dentro do container
      width: 40px; // Largura da esfera
      height: 40px; // Altura da esfera
      border-radius: 50%; // Deixa a esfera circular
      animation-duration: 2s; // Duração da animação
      animation-iteration-count: infinite; // Animação infinita
      animation-timing-function: ease-in-out; // Suaviza a entrada e saída da animação
    }

    .sphere.left {
      left: 0; // Posiciona à esquerda do container
      top: 50%; // Na linha central vertical
      background-color: red; // Cor vermelha
      animation-name: move-up-down; // Nome da animação aplicada
      animation-delay: 0s; // Sem atraso, começa imediatamente
    }

    .sphere.right {
      right: 0; // Posiciona à direita do container
      top: 50%; // Na linha central vertical
      background-color: blue; // Cor azul
      animation-name: move-up-down; // Mesma animação que a esquerda
      animation-delay: -1s; // Começa a animação 1s antes (efeito alternado)
    }

    @keyframes move-up-down {
      0%, 100% {
        transform: translateY(0); // Posição original
      }
      50% {
        transform: translateY(-100px); // Move 100px para cima no meio da animação
      }
    }

    @keyframes move-side {
      0%, 100% {
        transform: translate(-50%, -50%) translateX(0px); // Posição original
      }
      50% {
        transform: translate(-50%, -50%) translateX(20px); // Move 20px para a direita no meio da animação
      }
    }
  </style>
</head>
<body>
  <div class="container"> <!-- Container central dos elementos -->
    <div class="sphere left"></div> <!-- Esfera vermelha à esquerda -->
    <div class="person"></div> <!-- Imagem do personagem central -->
    <div class="sphere right"></div> <!-- Esfera azul à direita -->
  </div>
</body>
</html>
