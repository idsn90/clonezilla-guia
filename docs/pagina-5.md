# Parte 1 — Página 5  
# Backup Completo de Dispositivos — Salvando em Servidor Remoto via SSH

Nesta parte do guia, veremos como salvar um **backup completo do disco** diretamente em uma máquina remota utilizando **SSH**, garantindo segurança e integridade dos dados durante a transferência.

Este é um dos métodos mais usados em ambientes corporativos.

---

# 🔹 Pré-requisitos

Para o backup via SSH funcionar corretamente:

- Servidor remoto deve estar **na mesma rede**
- O servidor deve ter **SSH ativo**
- O usuário do servidor precisa ter **permissão de escrita** no diretório escolhido
- Rede deve ter DHCP (ou configurar manualmente)

---

# 🔹 Parâmetros usados no exemplo

- IP da máquina rodando Clonezilla: **192.168.56.10**  
- IP do servidor SSH remoto: **192.168.56.11**  
- Usuário no servidor SSH: **edson**  
- Porta SSH: **22**  
- Diretório remoto: **/home/edson/clonezilla**

---

# 🔹 Passo 1 — Selecionar o modo de operação

Escolha: device-image

![device-image](../images/pagina-5/pag5-image1.png)

---

# 🔹 Passo 2 — Selecionar o tipo de armazenamento

Escolha: ssh_server

![ssh_server](../images/pagina-5/pag5-image2.png)

---

# 🔹 Passo 3 — Informar o IP do servidor SSH

Digite o IP do servidor onde o backup será salvo.

Exemplo: 192.168.56.11 

![IP SSH](../images/pagina-5/pag5-image3.png)

---

# 🔹 Passo 4 — Informar a porta SSH

Na maioria dos casos: Porta 22

![Porta SSH](../images/pagina-5/pag5-image4.png)

---

# 🔹 Passo 5 — Informar o nome do usuário SSH

Digite o nome do usuário autorizado no servidor remoto.

Exemplo: edson

![Usuário SSH](../images/pagina-5/pag5-image5.png)

---

# 🔹 Passo 6 — Informar o diretório de destino no servidor

O caminho deve ser **absoluto** e o usuário deve ter direito de escrita.

Exemplo: /home/edson/clonezilla

![Diretório remoto](../images/pagina-5/pag5-image6.png)

---

# 🔹 Passo 7 — Autenticação SSH

Digite a senha do usuário quando solicitado.

![Autenticação SSH](../images/pagina-5/pag5-image7.png)
![Expert](../images/pagina-5/pag5-image8.png)

Pressione Enter para continuar.

---

# 🔹 Passo 8 — Selecionar o modo de execução

Escolha: Expert

![savedisk](../images/pagina-5/pag5-image9.png)

---

# 🔹 Passo 9 — Selecionar o tipo de backup

Como o backup será do disco inteiro: Savedisk

![Nome do backup](../images/pagina-5/pag5-image10.png)

---

# 🔹 Passo 10 — Nome do arquivo de backup

Defina um nome descritivo.

Exemplo:  ssh-image-disk-2012-11-28-01-img

![Origem do disco](../images/pagina-5/pag5-image11.png)

---

# 🔹 Passo 11 — Selecionar o disco de origem

Exemplo: sda

![Prioridade](../images/pagina-5/pag5-image12.png)

---

# 🔹 Passo 12 — Ajustar prioridade

Recomendado: -q2

![Parâmetros extras](../images/pagina-5/pag5-image13.png)

---

# 🔹 Passo 13 — Parâmetros adicionais

Mantenha os padrões marcados (-c e j2).

![gzip](../images/pagina-5/pag5-image14.png)

---

# 🔹 Passo 14 — Tipo de compressão

Recomendado: -z1

![Split size](../images/pagina-5/pag5-image15.png)

---

# 🔹 Passo 15 — Divisão da imagem (opcional)

Recomendado para grandes arquivos: 3000

![Skip checking](../images/pagina-5/pag5-image16.png)

---

# 🔹 Passo 16 — Verificação do sistema de arquivos

Escolha: 

![Verificação](../images/pagina-5/pag5-image17.png)

---

# 🔹 Passo 17 — Verificar imagem gerada

Escolha: 

E após finalização: Sim, verificar a imagem salva

![Backup via SSH 1](../images/pagina-5/pag5-image18.png)

Pressione Enter e confirme com **y**.

---

# 🔹 Processo de Backup via SSH

O Clonezilla enviará dados criptografados via SSH:

![Backup via SSH 2](../images/pagina-5/pag5-image19.png)

No servidor remoto, a pasta será preenchida:

![Arquivos no servidor SSH](../images/pagina-5/pag5-image20.png)

---

📌 O backup foi salvo com sucesso no servidor SSH.

---

➡ **[Próxima Página → Restauração via SSH](pagina-6.md)**  
⬅ **[Voltar para Página 4](pagina-4.md)**
