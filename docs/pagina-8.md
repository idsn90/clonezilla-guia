# Parte 1 — Página 8  
# Restauração de Imagens de Backup Salvas em Servidor Samba

Nesta parte veremos como restaurar um backup completo armazenado em um **servidor Samba (SMB)** para um disco local usando o Clonezilla Live.

Esse procedimento é muito útil em redes Windows ou ambientes mistos, onde o backup é centralizado em um compartilhamento de arquivos.

---

# 🔹 Pré-requisitos

Antes de iniciar:

- Máquina Clonezilla e servidor Samba devem estar na **mesma rede**
- Servidor Samba deve estar ativo
- Compartilhamento deve estar com:
  - **permissão de leitura** para o usuário Samba
  - caminho correto (ex: `/clonezilla`)
- Usuário Samba deve estar cadastrado
- Rede deve ter DHCP (ou configurar IP manualmente)

---

# 🔹 Configuração do exemplo

- IP da máquina Clonezilla: **192.168.56.12**  
- IP do servidor Samba: **192.168.56.11**  
- Usuário Samba: **edson**  
- Compartilhamento:

[clonezilla]
path = /home/edson/clonezilla
valid users = edson
writable = yes

---

# 🔹 Passo 1 — Selecionar modo de operação

Escolha: device-image

![device-image](../images/pagina-8/pag8-image1.png)

---

# 🔹 Passo 2 — Selecionar o tipo de acesso

Escolha: samba_server

![samba_server](../images/pagina-8/pag8-image2.png)

---

# 🔹 Passo 3 — Informar o IP do servidor Samba

Insira: 192.168.56.11

![IP Samba](../images/pagina-8/pag8-image3.png)

Pressione Enter (domínio pode ser deixado em branco).

---

# 🔹 Passo 4 — Informar o usuário Samba

Insira o usuário autorizado: edson

![Usuário Samba](../images/pagina-8/pag8-image4.png)

---

# 🔹 Passo 5 — Informar o compartilhamento remoto

⚠️ IMPORTANTE  
O nome do compartilhamento deve começar com `/`.

Exemplo: /clonezilla

![Compartilhamento Samba](../images/pagina-8/pag8-image5.png)

---

# 🔹 Passo 6 — Inserir senha do usuário Samba

Digite a senha quando solicitado.

![Senha Samba](../images/pagina-8/pag8-image6.png)

![Senha Samba](../images/pagina-8/pag8-image7.png)

---

# 🔹 Passo 7 — Selecionar o modo de execução

Escolha: Expert

![Modo Expert](../images/pagina-8/pag8-image8.png)

---

# 🔹 Passo 8 — Selecionar tipo de operação

Escolha: restoredisk

Assim a imagem será restaurada para o disco local.

![restoredisk](../images/pagina-8/pag8-image9.png)

---

# 🔹 Passo 9 — Selecionar a imagem de backup

O Clonezilla listará todas as imagens disponíveis no servidor Samba.

![Lista de backups](../images/pagina-8/pag8-image10.png)

Selecione a imagem desejada.

---

# 🔹 Passo 10 — Selecionar o disco destino

Exemplo: sdb

⚠️ O conteúdo do disco será totalmente sobrescrito.

![Disco destino](../images/pagina-8/pag8-image11.png)

---

# 🔹 Passo 11 — Ajuste dos parâmetros avançados

Desabilite:

- `g auto` → não reinstalar GRUB  
- `e1 auto` → usado apenas em NTFS  
- `e2` → evita uso de SFDISK alternativo  

Mantenha **marcado**:

- `-j2` → importante para manter o boot funcional

![Parâmetros avançados](../images/pagina-8/pag8-image12.png)

---

# 🔹 Passo 12 — Configurar tabela de partição

Escolha: -k1

Isso cria uma tabela de partição proporcional ao disco de destino.

![Parâmetro -k1](../images/pagina-8/pag8-image13.png)

---

# 🔹 Passo 13 — Ação após restauração

Escolha: -p true

![Parâmetro -p true](../images/pagina-8/pag8-image14.png)

---

# 🔹 Passo 14 — Confirmações finais

O Clonezilla pedirá confirmações:

- Pressione **Enter** quando solicitado  
- Digite **y** duas vezes para confirmar  

![Confirmação 1](../images/pagina-8/pag8-image15.png)

---

# 🔹 Processo de restauração em andamento

A imagem será copiada do servidor Samba e restaurada para o disco local.

![Restauração Samba](../images/pagina-8/pag8-image16.png)

---

📌 Após finalizar, o disco estará restaurado e pronto para uso.

---

➡ **[Próxima Página → Conclusão](pagina-9.md)**  
⬅ **[Voltar para Página 7](pagina-7.md)**


















