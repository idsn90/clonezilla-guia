# Parte 1 — Página 3  
# Backup Completo de Dispositivos Locais (device-image)

Nesta seção veremos como usar o Clonezilla Live para criar um **backup completo** de um dispositivo local, salvando a imagem diretamente em um disco conectado na máquina (HD, SSD, pendrive, etc).

O exemplo mostra backup de **uma partição**, mas o processo para backup de **um disco inteiro** é praticamente idêntico.

---

# 🔹 Passo 1 — Selecionar o modo de operação

Selecione:

Este modo é utilizado para **criar imagens de backup** ou **restaurar imagens já existentes**.

![device-image](../images/pagina-3/pag3-image1.png)

---

# 🔹 Passo 2 — Selecionar onde salvar o backup

Escolha:

Isso indica que a imagem será salva em um dispositivo conectado diretamente à máquina.

![local_dev](../images/pagina-3/pag3-image2.png)

Aguarde alguns segundos para montar pendrives e discos USB.

---

# 🔹 Passo 3 — Escolher a partição onde o backup será salvo (destino)

O Clonezilla listará todas as partições disponíveis.

⚠️ Não mostra partições SWAP.

Exemplo:

![Seleção de partição destino](../images/pagina-3/pag3-image3.png)

---

# 🔹 Passo 4 — Selecionar o diretório de destino

Selecione a pasta onde será gravada a imagem.

Se o disco só tem uma pasta, ela aparecerá automaticamente.

![Selecionar diretório](../images/pagina-3/pag3-image4.png)

Pressione Enter para continuar.

---

# 🔹 Passo 5 — Selecionar modo de execução

Escolha:

Assim podemos personalizar parâmetros importantes.

![Modo Expert](../images/pagina-3/pag3-image5.png)

---

# 🔹 Passo 6 — Escolher o tipo de backup

Como o backup será de uma **partição**, selecione:

Para backup de disco completo, seria:

![saveparts](../images/pagina-3/pag3-image6.png)

---

# 🔹 Passo 7 — Nome da imagem de backup

Defina um nome descritivo, por exemplo:

![Nome do backup](../images/pagina-3/pag3-image7.png)

---

# 🔹 Passo 8 — Selecionar a partição de origem (que será copiada)

Exemplo:

![Origem do backup](../images/pagina-3/pag3-image8.png)

---

# 🔹 Passo 9 — Ajuste de prioridade (opcional)

Para dar prioridade ao Partclone:

![Prioridade q2](../images/pagina-3/pag3-image9.png)

---

# 🔹 Passo 10 — Parâmetros importantes

Deixe habilitados:

- `-c`  
- `-j2`  

![Parâmetros -c e -j2](../images/pagina-3/pag3-image10.png)

---

# 🔹 Passo 11 — Tipo de compressão

Escolha o tipo de compressão, recomendamos:

Equilíbrio ideal entre tamanho e velocidade.

![gzip](../images/pagina-3/pag3-image11.png)

---

# 🔹 Passo 12 — Divisão do arquivo (opcional)

Define o tamanho máximo de cada parte do backup.

Recomendado para grandes imagens:

![Split size](../images/pagina-3/pag3-image12.png)

---

# 🔹 Passo 13 — Verificação do sistema de arquivos

Escolha:

![Skip checking](../images/pagina-3/pag3-image13.png)

---

# 🔹 Passo 14 — Verificação da imagem gerada

Selecione:

![Verificação](../images/pagina-3/pag3-image14.png)

Defina o que fazer ao final do processo:

(significa: não fazer nada)

---

# 🔹 Passo 15 — Processo de backup e verificação

O Clonezilla começará:

- Copiando blocos  
- Compactando  
- Dividindo arquivos (se configurado)  
- Verificando integridade

![Backup em andamento](../images/pagina-3/pag3-image15.png)

![Verificação final](../images/pagina-3/pag3-image16.png)

---

📌 A imagem agora está salva e pronta para ser restaurada quando necessário.

---

➡ **[Próxima Página → Restauração Local](pagina-4.md)**  
⬅ **[Voltar para Página 2](pagina-2.md)**
