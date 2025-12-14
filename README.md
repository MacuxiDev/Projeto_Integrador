Documentação do Projeto: BarberApp
1. Visão Geral
O BarberApp Lite é uma aplicação web responsiva (SPA - Single Page Application) para agendamento de serviços de barbearia.
Arquitetura: Client-Side (Sem servidor Backend).
Banco de Dados: JSON local persistido no navegador (localStorage).
Integração: Redirecionamento automático para WhatsApp para confirmação.
2. Pré-requisitos (Instalação Necessária)
Para rodar e editar este projeto, você precisa ter instalado no seu computador:
1.
Node.js (Versão 18 ou superior)
•
Para verificar se tem: Abra o terminal e digite node -v.
•
Onde baixar: nodejs.org
2.
Visual Studio Code (VS Code)
•
Onde baixar: code.visualstudio.com
3. Configuração do VS Code (Recomendado)
Para ter a melhor experiência de desenvolvimento, instale a seguinte extensão no VS Code:
Extensão: Tailwind CSS IntelliSense
Esta extensão ajuda a completar automaticamente as classes de estilo (cores, margens, fontes).
1.
No VS Code, clique no ícone de "Quadrados" na barra lateral esquerda (ou aperte Ctrl + Shift + X).
2.
Pesquise por: Tailwind CSS IntelliSense.
3.
Clique em Install.
4. Como Rodar o Projeto Localmente
Siga estes passos sempre que for trabalhar no projeto:
Passo 1: Abrir o Projeto
1.
Abra o VS Code.
2.
Vá em File > Open Folder (Arquivo > Abrir Pasta).
3.
Selecione a pasta barber-lite (ou barber-app).
Passo 2: Instalar Dependências (Apenas na primeira vez)
Se você acabou de baixar o projeto ou clonar o repositório, precisa baixar as bibliotecas:
1.
Abra o terminal do VS Code (Ctrl + ').
2.
Digite:
Bash
npm install
Passo 3: Iniciar o Servidor
Para ver o site funcionando:
1.
No terminal do VS Code, digite:
Bash
npm run dev
2.
O terminal mostrará algo como:
Local: http://localhost:5173/
3.
Segure a tecla Ctrl e clique nesse link, ou abra seu navegador e digite o endereço manualmente.
5. Banco de Dados e Armazenamento (JSON)
O aplicativo não usa um banco de dados externo (como MySQL). Ele usa o Local Storage do navegador. Isso significa que os dados ficam salvos no Chrome/Edge/Firefox do usuário.
Como visualizar e editar o Banco de Dados no Navegador:
1.
Com o projeto rodando no navegador, aperte F12 (ou clique com botão direito na página -> Inspecionar).
2.
Vai abrir as Ferramentas do Desenvolvedor (DevTools).
3.
No menu superior do DevTools, procure pela aba Application (Aplicativo).
Se não aparecer, clique nas duas setinhas >> para ver mais opções.
4.
Na coluna da esquerda, expanda a seção Local Storage.
5.
Clique no endereço (ex: http://localhost:5173).
Onde estão os dados?
Você verá uma tabela com Key (Chave) e Value (Valor).
Chave: barber_appointments
Valor: É o JSON contendo todos os agendamentos feitos.
Dica de Sênior:
Se você quiser limpar todos os agendamentos, clique com o botão direito em barber_appointments e selecione Delete. Ao recarregar a página (F5), o app estará zerado.
Você pode editar os dados (como mudar um nome ou data) clicando duas vezes no "Value", alterando o texto e dando Enter. Dê F5 na página para ver a mudança.
6. Solução de Problemas Comuns
Erro: "O arquivo npm.ps1 não pode ser carregado..."
Se o Windows bloquear o comando npm, é uma trava de segurança do PowerShell.
Solução:
1.
No terminal do VS Code, cole este comando e dê Enter:
PowerShell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
2.
Se perguntar, digite S ou Y para confirmar.
3.
Tente rodar npm run dev novamente.
Erro: Tela Branca ou "Cannot find module"
Isso geralmente acontece se o arquivo src/lib/db.ts estiver faltando ou com nome errado. Solução: Verifique se a pasta lib existe dentro de src e se o arquivo db.ts está lá com o código correto.
7. Estrutura de Arquivos Importantes
src/App.tsx: O coração do aplicativo. Contém as telas, o formulário e a lógica visual.
src/lib/db.ts: O cérebro dos dados. Contém a configuração dos serviços (SEED_SERVICES) e as funções de salvar/carregar.
src/index.css: Onde definimos os estilos globais do Tailwind.
tailwind.config.js: Configurações do sistema de design
