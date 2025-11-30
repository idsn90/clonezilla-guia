# Parte 1 — Página 2  
# Clonagem de Dispositivos

A clonagem de dispositivos é um dos principais recursos do Clonezilla.  
Ela permite replicar completamente um disco ou partição para outro disco/partição de tamanho igual ou maior — ideal para técnicos e usuários que não querem reinstalar sistemas em caso de falha.

📌 *Neste guia usaremos o Parted Magic, pois ele contém Clonezilla + GParted.*

---

# 🔹 Antes de começar

Certifique-se de que:

- O disco/partição **de destino é igual ou maior** que o de origem  
- O Clonezilla Live ou Parted Magic está em um pendrive  
- Os discos estão conectados corretamente  
- O disco de destino está **vazio ou pode ser sobrescrito**

---

# 🔹 Tela inicial do Clonezilla

![Clonezilla inicial](../images/pagina-2/pag2-image1.png)

Clique Enter para continuar.

---

# 🔹 Passo 1 — Selecione o modo de trabalho

O Clonezilla mostrará duas opções:

- **device-image** → trabalhar com imagens (backup/restauração)
- **device-device** → clone direto entre dispositivos

Selecionamos:

![Modo device-device](../images/pagina-2/pag2-image2.png)

---

# 🔹 Passo 2 — Escolha o modo de operação

O Clonezilla oferece dois modos:

- **Beginner** → configurações automáticas  
- **Expert** → permite personalização avançada  

Neste guia:  
📌 Escolheremos **Expert** para configurar parâmetros importantes.

![Expert mode](../images/pagina-2/pag2-image3.png)

---

# 🔹 Passo 3 — Escolha o tipo de clone

Selecione:

Isto clona **um disco inteiro para outro disco local**.

![disk_to_local_disk](../images/pagina-2/pag2-image4.png)

---

# 🔹 Passo 4 — Selecione o disco de origem

Informe qual disco será clonado.

Exemplo:

![Seleção do disco de origem](../images/pagina-2/pag2-image5.png)

---

# 🔹 Passo 5 — Selecione o disco de destino

O disco selecionado aqui será **totalmente sobrescrito**.

Exemplo:

![Seleção do disco de destino](../images/pagina-2/pag2-image6.png)

---

# 🔹 Passo 6 — Configuração dos parâmetros

Aqui você pode habilitar/desabilitar opções avançadas.

Para sistemas Windows/NTFS, desabilite:

- `g auto` → evita reinstalação do GRUB  
- `e2` → evita configurações especiais de bootloaders  

![Parâmetros avançados](../images/pagina-2/pag2-image7.png)

---

# 🔹 Passo 7 — Escolha o comportamento de verificação

Selecionar:

![Skip checking](../images/pagina-2/pag2-image8.png)

---

# 🔹 Passo 8 — Parâmetro de tabela de partição

Escolher:

⚠ Útil quando o disco de destino é maior.

⚠ Não recomendado em discos GPT dependendo da estrutura.

![Parâmetro -k1](../images/pagina-2/pag2-image9.png)

---

# 🔹 Passo 9 — Confirmação do clone

O Clonezilla pedirá confirmações:

- Pressione Enter quando solicitado  
- Digite **y** para confirmar  
- Em sistemas Windows, confirme clonagem do bootloader  

![Confirmação final](../images/pagina-2/pag2-image10.png)

---

# 🔹 Processo de clonagem em execução

O Clonezilla utiliza **Partclone** para copiar blocos usados.

![Clonagem em andamento](../images/pagina-2/pag2-image11.png)

---

# 🔹 Resultado final após o clone

Após o processo, veja o particionamento:

![Resultado da clonagem](../images/pagina-2/pag2-image12.png)

Partição clonada corretamente e pronta para uso.

---

# 🔹 Para clonar apenas a partição

Repita os mesmos passos, porém selecione:


E use o parâmetro:


![Clonagem de partição](../images/pagina-2/pag2-image13.png)

---

➡ **[Próxima Página → Backup Completo Local](pagina-3.md)**  
⬅ **[Voltar para Página 1](pagina-1.md)**

