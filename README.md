# I2A2 - Curso: Agentes Autônomos com Redes Generativas 
### _Professor Celso Azevedo_

__Grupo 296__
* Thais Santos
* Thais Petrin
* Pablo Juan Garcia
* João Junior
* Evandro Covre

### **Projeto:** _Agentes Autônomos - Análise de CSV_
__Estrutura__ 
* **N8N**: Ferramenta Low-code utilizada para orquestração do Agente
* **GoogleDrive**: Repositório on-line para armazenamento dos arquivos CSVs que serão processados pelo Agente
* **SUPABASE/POSTGRES**: Plataforma de back-end as a service utilizada para armazenamento dos dados do CSV para posterior processamento
* **GROQ**: Plataforma on-line que permite acessar modelos LLM de código aberto em ambiente on-line
* **llama3-8b-8192**: Modelo LLM utilizado para processamento dos prompts geração automática das consultas que traduzem a solicitação do usuário em código SQL nativo do banco de dados utilizado.

__Funcionamento__ 

O agente funciona diretamente com a interface de chat disponibilizada pelo próprio N8N, sendo que se o usuário enviar uma URL, ele entenderá que o usuário deseja fazer um processamento de dados e tentará fazer o download do arquivo, 
que necessáriamente tem que estar no GoogleDrive, processará os arquivos de nota e itens da Nota formanto uma tabela desnormalizada. 
Quando o usuário enviar uma pergunta, o agente assumirá o papel de um especialista em SQL e gerará a consulta SQL para retornar a solicitação do usuário. Após a geração do SQL, o agente encaminhará essa consulta para o Postgres, 
o resultado será encaminhado para outra LLM que transformará o resultado em um formato mais amigável para o usuário.
