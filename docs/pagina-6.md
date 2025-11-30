# Parte 1 — Página 6  
# Restauração de Imagens de Backup Salvas em Servidor SSH

Nesta página veremos como restaurar um backup completo que foi salvo remotamente via **SSH**, utilizando uma imagem armazenada em um servidor seguro na rede.

Este processo é ideal para infraestrutura corporativa, laboratórios e backups centralizados.

---

# 🔹 Pré-requisitos

Antes de iniciar, confirme:

- Servidor SSH está **ativo e acessível**
- O diretório remoto ainda contém a imagem
- O usuário tem **leitura** no diretório da imagem
- Servidor e máquina Clonezilla estão **na mesma rede**

---

# 🔹 Parâmetros do exemplo

- IP da máquina Clonezilla (origem da restauração): **192.168.56.10**  
- IP do servidor SSH que armazena a imagem: **192.168.56.11**  
- Usuário SSH: **edson**  
- Porta SSH: **22**  
- Diretório remoto usado: **/home/edson/clonezilla**

---

# 🔹 Passo 1 — Selecionar modo de operação

Escolha: device-image

![device-image](../images/pagina-6/pag6-image1.png)

---

# 🔹 Passo 2 — Selecionar o tipo de acesso

Escolha: ssh_server

![ssh_server](../images/pagina-6/pag6-image2.png)

---

# 🔹 Passo 3 — Informar o IP do servidor SSH

Exemplo: 192.168.56.11

![IP SSH](../images/pagina-6/pag6-image3.png)

---

# 🔹 Passo 4 — Informar a porta SSH

Exemplo: 22

![Porta SSH](../images/pagina-6/pag6-image4.png)

---

# 🔹 Passo 5 — Informar o usuário SSH

Exemplo: edson

![Usuário SSH](../images/pagina-6/pag6-image5.png)

---

# 🔹 Passo 6 — Informar o diretório onde a imagem está salva

Exemplo: /home/edson/clonezilla

![Diretório remoto](../images/pagina-6/pag6-image6.png)

---

# 🔹 Passo 7 — Autenticação SSH

Digite a senha quando solicitado.

![Autenticação SSH](../images/pagina-6/pag6-image7.png)

Pressione Enter para continuar.

---

# 🔹 Passo 8 — Selecionar modo de execução

Escolha: Expert

![Modo Expert](../images/pagina-6/pag6-image8.png)

---

# 🔹 Passo 9 — Tipo de operação a ser feita

Para restaurar disco inteiro, selecione: restoredisk

![restoredisk](../images/pagina-6/pag6-image9.png)

---

# 🔹 Passo 10 — Selecionar a imagem de backup

O Clonezilla listará as imagens disponíveis no servidor SSH.

Exemplo:

![Imagem selecionada](../images/pagina-6/pag6-image10.png)

Escolha a imagem desejada.

---

# 🔹 Passo 11 — Selecionar o disco destino da restauração

O disco escolhido será completamente sobrescrito.

Exemplo: sdc

![Disco destino](../images/pagina-6/pag6-image11.png)

---

# 🔹 Passo 12 — Ajustar parâmetros avançados

Desabilite:

- `g auto` → não reinstalar GRUB  
- `e1 auto` → usado apenas em NTFS  
- `e2` → evita uso especial do SFDISK  

Mantenha **marcado**:

- `-j2` → garante consistência do gerenciador de boot

![Parâmetros avançados](../images/pagina-6/pag6-image12.png)

---

# 🔹 Passo 13 — Configuração da tabela de partição

Escolha: -k1

Isso cria uma nova tabela de partições no disco de destino, ajustando proporcionalmente.

⚠ Pode não funcionar corretamente quando há partição SWAP no final da imagem.

![Parâmetro -k1](../images/pagina-6/pag6-image13.png)

---

# 🔹 Passo 14 — Ação após restauração

Escolha: -p true

![Ação pós-processo](../images/pagina-6/pag6-image14.png)

---

# 🔹 Passo 15 — Confirmar e iniciar a restauração

Pressione Enter sempre que solicitado e confirme com: y

![Confirmação 1](../images/pagina-6/pag6-image15.png)

![Confirmação 2](../images/pagina-6/pag6-image16.png)

---

# 🔹 Processo de restauração em andamento

![Restauração via SSH](../images/pagina-6/pag6-image17.png)

---

# 🔹 Resultado final

Se o disco conter uma partição SWAP no fim, a expansão automática pode falhar — exigindo ajuste manual via GParted.

![Resultado final](../images/pagina-6/pag6-image18.png)

---

➡ **[Próxima Página → Backup via Samba](pagina-7.md)**  
⬅ **[Voltar para Página 5](pagina-5.md)**










