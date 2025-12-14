Documentação do Projeto: BarberPlanner (PWA)
1. Visão Geral
O BarberPlanner é uma Aplicação Web Progressiva (PWA) desenvolvida para o gerenciamento completo de barbearias. Diferente da versão anterior ("Lite"), esta versão conta com sistema de autenticação, painel administrativo, gestão de equipe e prevenção de conflitos de horário.
•
Arquitetura: Client-Side (SPA) com capacidade de instalação (PWA).
•
Banco de Dados: LocalStorage (Simulação de persistência local para MVP).
•
Diferencial: Funciona offline, possui Login/Cadastro e Área do Dono.
2. Pré-requisitos (Instalação Necessária)
Para rodar e editar este projeto, você precisa ter instalado no seu computador:
1.
Node.js (Versão 18 ou superior)
•
Para verificar: Abra o terminal e digite node -v.
•
Download: nodejs.org.
2.
Git (Para clonar o repositório).
3.
Visual Studio Code (VS Code).
Configuração Recomendada do VS Code
Instale a extensão Tailwind CSS IntelliSense para facilitar a estilização.
1.
No VS Code, aperte Ctrl + Shift + X.
2.
Pesquise por: Tailwind CSS IntelliSense.
3.
Clique em Install.
3. Como Rodar o Projeto
Passo 1: Baixar o Código
Abra o terminal e clone o repositório (ou abra a pasta descompactada no VS Code):
Bash
git clone https://github.com/MacuxiDev/Projeto_Integrador.git
Passo 2: Instalar Dependências
Necessário apenas na primeira vez para baixar as bibliotecas do projeto.
1.
Abra o terminal do VS Code (Ctrl + ').
2.
Digite:
Bash
npm install
Passo 3: Iniciar o Servidor
Para ver o site funcionando:
1.
No terminal, digite:
Bash
npm run dev
2.
O terminal mostrará o link local: http://localhost:5173/.
3.
Segure Ctrl e clique no link para abrir no navegador.
4. Credenciais de Acesso (Importante)
Como o sistema utiliza um banco de dados local, utilize estas credenciais para acessar as funções restritas:
•
Acesso do Dono (Admin):
•
Clique no ícone de Cadeado na tela de Login ou Home.
•
Senha Mestra: admin123
5. Banco de Dados e Armazenamento
O aplicativo utiliza o Local Storage do navegador para persistir os dados.
Como visualizar e editar os dados:
1.
Com o projeto rodando, aperte F12 para abrir o DevTools.
2.
Vá na aba Application (Aplicativo).
3.
Na esquerda, expanda Local Storage e clique no endereço do site.
Principais Chaves (Keys) utilizadas:
•
barber_users: Lista de clientes cadastrados (JSON).
•
barber_appointments: Lista de todos os agendamentos.
•
barber_staff: Lista de barbeiros (Equipe).
•
barber_current_user: Sessão do usuário logado atualmente.
Dica: Para resetar o sistema completamente, clique com o botão direito nas chaves e selecione Delete, depois recarregue a página com F5.
6. Estrutura de Arquivos Importantes
A estrutura foi atualizada para suportar as novas funcionalidades:
•
src/App.tsx: Gerencia a navegação (Roteamento), Telas de Login, Cadastro, Home e Painel Admin.
•
src/lib/db.ts: Contém toda a lógica de negócio (Salvar agendamento, Validar conflito de horário, Login, Registro) e dados iniciais (SEED_SERVICES).
•
vite.config.ts: Configuração do PWA e do servidor de desenvolvimento.
•
public/: Contém os ícones (pwa-192x192.png) necessários para a instalação no celular.
7. Solução de Problemas Comuns
Erro: "O arquivo npm.ps1 não pode ser carregado..." Se o PowerShell bloquear o comando:
1.
No terminal do VS Code, execute:
PowerShell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
2.
Confirme com S ou Y.
Erro: Tela Branca ao rodar Geralmente ocorre por erro na importação do banco de dados. Verifique se o arquivo src/lib/db.ts existe e não possui erros de sintaxe.
Erro: Alterações no código não aparecem Como é um PWA, o navegador pode estar usando uma versão antiga em cache.
•
Solução: Abra o DevTools (F12) > Application > Service Workers > Marque a caixa "Update on reload".
