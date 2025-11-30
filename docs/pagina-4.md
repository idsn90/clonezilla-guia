# Parte 1 — Página 4  
# Restaurando Imagens de Backup em Dispositivos Locais

Nesta página veremos como restaurar uma imagem criada anteriormente usando o modo **device-image**, armazenada em um dispositivo local.

Este processo serve tanto para restauração de **partições individuais** quanto de **discos inteiros**.

---

# 🔹 Passo 1 — Selecionar o modo de operação

Escolha:

Isso indica que vamos **restaurar** uma imagem de backup salva anteriormente.

![Modo device-image](../images/pagina-4/pag4-image2.png)

---

# 🔹 Passo 2 — Selecionar onde está armazenada a imagem

Selecione:

Este é o modo para montar um dispositivo local contendo a imagem de backup.

![local_dev](../images/pagina-4/pag4-image3.png)

Se estiver usando pendrive, aguarde 5 segundos e pressione Enter para montar.

---

# 🔹 Passo 3 — Selecionar a partição que contém a imagem  
Exemplo:

Onde você salvou a imagem anteriormente.

![Selecionar partição](../images/pagina-4/pag4-image4.png)

---

# 🔹 Passo 4 — Selecionar o diretório que contém a imagem

Selecione a pasta onde a imagem foi salva.

Se foi no diretório raiz `/`, selecione-o.

![Selecionar diretório](../images/pagina-4/pag4-image5.png)

Pressione Enter para continuar.

---

# 🔹 Passo 5 — Selecionar o modo de execução

Escolha:

Assim você controla parâmetros importantes.

![Modo Expert](../images/pagina-4/pag4-image6.png)

---

# 🔹 Passo 6 — Escolher o tipo de restauração

Para restaurar uma **partição**, selecione:

Para restaurar um **disco completo**, usaria:

![restoreparts](../images/pagina-4/pag4-image7.png)

---

# 🔹 Passo 7 — Selecionar a imagem de backup

Será listado o backup salvo anteriormente.

Exemplo:

![Selecionar a imagem](../images/pagina-4/pag4-image8.png)

---

# 🔹 Passo 8 — Selecionar a partição de destino

Esta partição será **sobrescrita totalmente**.

Exemplo:

![Selecionar destino](../images/pagina-4/pag4-image9.png)

---

# 🔹 Passo 9 — Configurar parâmetros avançados

Desabilite:

- `g auto` → evita reinstalar o GRUB  
- `e1 auto` → usado somente em NTFS  
- `e2` → evita uso do SFDISK especial  

Mantenha habilitado:

- `-j2` → necessário para boot funcionar

![Parâmetros avançados](../images/pagina-4/pag4-image10.png)

Pressione Enter.

---

# 🔹 Passo 10 — Configurar tabela de partição

Como estamos restaurando **uma única partição**, escolha:

Assim NÃO será criada nova tabela de partição.

Para discos inteiros, usaríamos `-k1`.

![Parâmetro -k](../images/pagina-4/pag4-image11.png)

Configure também:

Para não executar nenhuma ação após finalizar.

---

# 🔹 Passo 11 — Confirmar e iniciar a restauração

Pressione:

- **Enter** sempre que solicitado  
- **y** para confirmar operações destrutivas  

A restauração iniciará:

![Restauração em andamento](../images/pagina-4/pag4-image12.png)

---

# 🔹 Resultado final da restauração

Depois do processo, a partição destino estará idêntica à partição salva no backup.

Você pode visualizar no particionamento:

![Partição restaurada](../images/pagina-4/pag4-image13.png)

---

➡ **[Próxima Página → Backup via SSH](pagina-5.md)**  
⬅ **[Voltar para Página 3](pagina-3.md)**
