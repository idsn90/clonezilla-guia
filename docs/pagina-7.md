# Parte 1 — Página 7  
# Backup Completo de Dispositivos — Salvando em Servidor Samba

Nesta parte do guia veremos como salvar um **backup completo do disco** em um servidor remoto utilizando o protocolo **Samba (SMB)**.  
Esse método é muito utilizado em redes corporativas Windows ou ambientes mistos.

---

# 🔹 Pré-requisitos

Antes de iniciar o processo:

- Servidor Samba deve estar **na mesma rede**
- Compartilhamento Samba deve ter:
  - Permissão de escrita
  - Usuário cadastrado
  - Diretório acessível
- Serviço Samba em funcionamento (smbd)
- Rede com DHCP (ou configurar Clonezilla manualmente)

---

# 🔹 Configuração usada no exemplo

- IP da máquina Clonezilla: **192.168.56.12**  
- IP do servidor Samba: **192.168.56.11**  
- Compartilhamento Samba:

[clonezilla]
path = /home/edson/clonezilla
valid users = edson
writable = yes

- Usuário Samba: **edson**

---

# 🔹 Passo 1 — Selecionar o modo de operação

Escolha: device-image

![device-image](../images/pagina-7/pag7-image1.png)

---

# 🔹 Passo 2 — Selecionar o tipo de armazenamento

Selecione: samba_server

![samba_server](../images/pagina-7/pag7-image2.png)

---

# 🔹 Passo 3 — Informar o IP do servidor Samba

Exemplo: 192.168.56.11

![IP Samba](../images/pagina-7/pag7-image3.png)

Pressione Enter (domínio pode ser ignorado ao usar IP).

---

# 🔹 Passo 4 — Informar o usuário Samba

Exemplo: edson

![Usuário Samba](../images/pagina-7/pag7-image4.png)

---

# 🔹 Passo 5 — Informar o nome do compartilhamento

⚠️ IMPORTANTE  
O nome do compartilhamento deve iniciar com **/**:

Exemplo: /clonezilla

![Compartilhamento Samba](../images/pagina-7/pag7-image5.png)

---

# 🔹 Passo 6 — Inserir a senha do usuário Samba

Após inserir, pressione Enter.

![Senha Samba](../images/pagina-7/pag7-image6.png)

---

# 🔹 Passo 7 — Selecionar modo de execução

Escolha: Expert

![Modo Expert](../images/pagina-7/pag7-image7.png)

---

# 🔹 Passo 8 — Selecionar tipo de operação

Escolha: savedisk

Para salvar um backup completo do **disco local**.

![savedisk](../images/pagina-7/pag7-image8.png)

---

# 🔹 Passo 9 — Definir nome da imagem de backup

Escolha um nome descritivo, por exemplo: backup_sda_samba_2025

![Nome do backup](../images/pagina-7/pag7-image9.png)

---

# 🔹 Passo 10 — Selecionar o disco de origem

Exemplo: sda

![Origem](../images/pagina-7/pag7-image10.png)

---

# 🔹 Passo 11 — Ajustar prioridade

Recomendado: -q2

![Prioridade](../images/pagina-7/pag7-image11.png)

---

# 🔹 Passo 12 — Parâmetros adicionais

Mantenha as opções padrão marcadas.

![Parâmetros padrão](../images/pagina-7/pag7-image12.png)

---

# 🔹 Passo 13 — Tipo de compressão

Escolha: -z1 (gzip)

![gzip](../images/pagina-7/pag7-image13.png)

---

# 🔹 Passo 14 — Dividir arquivo (opcional)

Recomendado: 3000 MB

![Split size](../images/pagina-7/pag7-image14.png)

---

# 🔹 Passo 15 — Verificar sistema de arquivos

Escolha: Skip checking/repairing source file system

![Skip check](../images/pagina-7/pag7-image15.png)

---

# 🔹 Passo 16 — Verificar imagem final

Escolha: Sim, verificar a imagem salva

E pós-processo: -p true

![Verificação](../images/pagina-7/pag7-image16.png)

---

# 🔹 Processo de backup em andamento

O Clonezilla realizará:

- Leitura do disco
- Compactação
- Divisão (se configurado)
- Envio dos arquivos ao Samba

![Backup Samba 1](../images/pagina-7/pag7-image17.png)

![Backup Samba 2](../images/pagina-7/pag7-image18.png)

---

📌 Backup completo salvo com sucesso no servidor Samba!

---

➡ **[Próxima Página → Restauração via Samba](pagina-8.md)**  
⬅ **[Voltar para Página 6](pagina-6.md)**















