# -cidadaniadigital2026.
├── index.html
├── css/
│   └── style.css
├── js/
│   └── script.js
└── README.md
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cidadania Digital & IA</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

    <header>
        <h1>Consciência Digital</h1>
        <p>O Impacto das Deepfakes e da Desinformação na Sociedade</p>
        <button id="toggle-dark-mode">Alternar Modo Escuro</button>
    </header>

    <main>
        <section id="introducao">
            <h2>O que são Deepfakes?</h2>
            <p>Deepfakes são vídeos, áudios ou imagens manipulados por Inteligência Artificial para fazer pessoas parecerem dizer ou fazer coisas que nunca fizeram. Embora a tecnologia seja fascinante, ela traz grandes riscos para a verdade e a segurança digital.</p>
        </section>

        <section id="quiz-section">
            <h2>Desafio: Você sabe identificar uma Fake News?</h2>
            <p>Responda à pergunta abaixo para testar seus conhecimentos:</p>
            
            <form id="quiz-form">
                <p><strong>Pergunta:</strong> Se você receber uma notícia bombástica com um link estranho no WhatsApp, o que deve fazer?</p>
                <label>
                    <input type="radio" name="pergunta1" value="errado"> Compartilhar imediatamente com os amigos.
                </label><br>
                <label>
                    <input type="radio" name="pergunta1" value="certo"> Pesquisar em sites de checagem confiáveis antes de repassar.
                </label><br>
                <button type="submit">Verificar Resposta</button>
            </form>
            <div id="quiz-resultado"></div>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 - Desenvolvido para o Componente de Educação Digital e IA</p>
    </footer>

    <script src="js/script.js"></script>
</body>
</html>
/* Configurações Gerais e Cores */
:root {
    --bg-color: #f4f4f9;
    --text-color: #333;
    --card-bg: #ffffff;
    --primary-color: #007bcc;
}

[data-theme="dark"] {
    --bg-color: #1e1e24;
    --text-color: #f4f4f9;
    --card-bg: #2a2a35;
    --primary-color: #4da6ff;
}

body {
    font-family: Arial, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    margin: 0;
    padding: 0;
    transition: background 0.3s, color 0.3s;
}

header {
    background-color: var(--primary-color);
    color: white;
    padding: 2rem;
    text-align: center;
}

main {
    display: flex;
    flex-direction: column;
    gap: 20px;
    max-width: 800px;
    margin: 20px auto;
    padding: 0 15px;
}

section {
    background-color: var(--card-bg);
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}

button {
    background-color: var(--primary-color);
    color: white;
    border: none;
    padding: 10px 15px;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 10px;
}

button:hover {
    opacity: 0.9;
}

/* Responsividade (Media Queries) */
@media (min-width: 768px) {
    main {
        flex-direction: row;
        flex-wrap: wrap;
    }
    section {
        flex: 1 1 45%;
    }
}
document.addEventListener('DOMContentLoaded', () => {
    // 1. Funcionalidade do Modo Escuro
    const toggleBtn = document.getElementById('toggle-dark-mode');
    
    toggleBtn.addEventListener('click', () => {
        const currentTheme = document.body.getAttribute('data-theme');
        if (currentTheme === 'dark') {
            document.body.removeAttribute('data-theme');
        } else {
            document.body.setAttribute('data-theme', 'dark');
        }
    });

    // 2. Validação do Formulário / Quiz
    const quizForm = document.getElementById('quiz-form');
    const resultadoDiv = document.getElementById('quiz-resultado');

    quizForm.addEventListener('submit', (event) => {
        event.preventDefault(); // Impede a página de recarregar
        
        const respostaSelecionada = quizForm.elements['pergunta1'].value;
        
        if (!respostaSelecionada) {
            resultadoDiv.innerHTML = "<p style='color: orange;'>Por favor, selecione uma opção!</p>";
            return;
        }

        if (respostaSelecionada === 'certo') {
            resultadoDiv.innerHTML = "<p style='color: green; font-weight: bold;'>Correto! Sempre cheque as fontes em canais oficiais.</p>";
        } else {
            resultadoDiv.innerHTML = "<p style='color: red; font-weight: bold;'>Incorreto. Compartilhar sem checar espalha desinformação.</p>";
        }
    });
});
# Cidadania Digital e Inteligência Artificial

## 🎯 Objetivo do Projeto
Este site foi desenvolvido como atividade de Recuperação Prática para o componente de Educação Digital e IA. O objetivo principal é conscientizar a comunidade escolar sobre os perigos das Deepfakes, a automação das Fake News e apresentar boas práticas de segurança e checagem de fatos na internet.

## 🛠️ Tecnologias Utilizadas
- HTML5 (Estruturação Semântica)
- CSS3 (Estilização Responsiva com Flexbox)
- JavaScript Vanilla (Interatividade do Quiz e Modo Escuro)

## 🤖 Uso de Inteligência Artificial e Créditos
Para a construção deste projeto, utilizei assistentes de IA para geração e refinamento de partes do código e textos. Abaixo estão os comandos exatos utilizados:

- **Prompt para o código base:** *"Crie uma estrutura de site em HTML, CSS e JavaScript sobre Cidadania Digital e IA, contendo um quiz de perguntas e respostas e um botão de alternar tema escuro."*
