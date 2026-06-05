# Trabalho de Grupo - Tópico 03

## Plano de criação e publicação de serviço web

### 1. Identificação do grupo

* **Grupo:** Breakout 4
* **Elementos:**

  * Carlina Pinto
  * Anne Gomes
  * Bruno Veiga

### 2. Serviço escolhido

O grupo escolheu a **Opção A - Página HTML simples**.

Esta opção foi escolhida por ser adequada a uma publicação essencial em ambiente Linux. O objetivo foi publicar uma página simples, validar o funcionamento do serviço web e documentar as principais decisões técnicas.

### 3. Rota de publicação

A rota escolhida foi:

**Nginx**

O Nginx foi utilizado como servidor web para disponibilizar uma página HTML simples através do protocolo HTTP.

### 4. Arquitetura de publicação

Fluxo da publicação:

```text
Cliente/Navegador -> HTTP -> Porta 80 -> Nginx -> Ficheiro HTML
```

O utilizador acede ao endereço público do servidor através do navegador. O pedido HTTP chega à porta 80 do servidor. A firewall UFW permite a entrada desse tráfego e o Nginx responde com o ficheiro HTML publicado no diretório `/var/www/html`.

### 5. Componentes utilizados

* Servidor Ubuntu em ambiente cloud
* Acesso remoto por SSH
* Utilizador com permissões sudo
* Nginx como servidor web
* UFW como firewall
* Página HTML simples
* GitHub para documentação e submissão

### 6. Validação realizada

Foram realizados testes para confirmar que o serviço web estava funcional:

* Validação do estado do Nginx com `systemctl status nginx`
* Validação da firewall com `sudo ufw status verbose`
* Teste local com `curl http://localhost`
* Teste através do IP público com `curl http://IP_DO_SERVIDOR`
* Teste no navegador através de `http://IP_DO_SERVIDOR`

### 7. Evidências

As evidências do trabalho encontram-se na pasta:

```text
evidencias/
```

Exemplos de evidências recolhidas:

* Nginx ativo no servidor
* UFW ativa com OpenSSH e porta 80 permitidos
* Página HTML publicada no servidor
* Teste com `curl http://localhost`
* Teste com `curl http://IP_DO_SERVIDOR`
* Página aberta no navegador

### 8. Relatório

O relatório em PDF encontra-se neste diretório com o nome:

```text
grupo-3-publicacao-servico-web-topico-03.pdf
```

### 9. Segurança

Antes da publicação no GitHub, o grupo confirmou que não foram incluídos dados sensíveis, tais como:

* Passwords
* Chaves privadas SSH
* Tokens
* Dados de pagamento
* Credenciais de base de dados
* Ficheiros `.env`
* Informações privadas de acesso ao servidor

### 10. Conclusão

O grupo publicou uma página HTML simples utilizando Nginx num servidor Ubuntu em ambiente cloud. A solução permitiu aplicar conceitos de publicação web, HTTP, porta 80, SSH, firewall UFW, validação com terminal e navegador, e documentação no GitHub.
