<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=24&pause=1000&color=F97316&center=true&vCenter=true&width=650&height=60&lines=Automa%C3%A7%C3%A3o+de+Infraestrutura+Linux;Python+%2B+Paramiko+%2B+Debian;Flutter+%2B+Firebase+%2B+IA+on-device;Menos+tarefa+manual%2C+mais+c%C3%B3digo" alt="Automação de Infraestrutura Linux" />

### 👋 Olá, eu sou o **Lucas Mueller**

<img alt="Local" src="https://img.shields.io/badge/Jaraguá_do_Sul-SC,_Brasil-374151?style=for-the-badge&logo=googlemaps&logoColor=F97316">
<img alt="Foco" src="https://img.shields.io/badge/Foco-Automação_&_Infra-F97316?style=for-the-badge&logo=gnubash&logoColor=white">
<img alt="Formação" src="https://img.shields.io/badge/Eng._de_Software-CatólicaSC-FBBF24?style=for-the-badge&logo=googlescholar&logoColor=black">

</div>

---

## 🎯 Sobre

Trabalho com **automação e infraestrutura Linux** na Prefeitura de Jaraguá do Sul, onde meu foco é simples: **toda tarefa manual repetitiva é um bug de processo esperando virar script.**

Meu dia a dia é manter um parque de máquinas Debian atualizado, inventariado e monitorado — sem depender de alguém sentar em cada estação. Para isso escrevo ferramentas em Python que conversam com a rede via SSH e SNMP, geram relatórios auditáveis e entregam para a equipe de TI a visibilidade que antes só existia em planilha preenchida na mão.

Fora do trabalho, estou concluindo **Engenharia de Software** e construindo o ObraFácil — um app Flutter que roda **IA direto no dispositivo**, sem nuvem, porque canteiro de obra costuma ser exatamente onde a internet não chega.

```yaml
localizacao:  Jaraguá do Sul, SC — Brasil
atuacao:      Automação de Infraestrutura & Desenvolvimento
ambiente:     Debian Linux · Python · SSH · SNMP
estudando:    Engenharia de Software — CatólicaSC
principio:    "Se eu fiz duas vezes na mão, na terceira vira código."
```

---

## 🚀 Projetos em Destaque

<table>
<tr>
<td width="50%" valign="top">

#### 🏗️ [ObraFácil](https://github.com/LucasMueller134/Obrafacil)

<img alt="Dart" src="https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white"> <img alt="Flutter" src="https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white"> <img alt="Firebase" src="https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black">

Gestão de obras com **IA rodando offline no celular**. Lê nota fiscal por foto, aceita lançamento por voz e prevê estouro de orçamento — tudo sem internet.

`98 testes` · `~14.4k linhas` · `CI com build de APK`

</td>
<td width="50%" valign="top">

#### 🐧 [linux-system-updater](https://github.com/LucasMueller134/linux-system-updater)

<img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"> <img alt="Debian" src="https://img.shields.io/badge/Debian-A81D33?style=flat-square&logo=debian&logoColor=white"> <img alt="SSH" src="https://img.shields.io/badge/SSH-000000?style=flat-square&logo=openssh&logoColor=white">

Atualiza um **parque inteiro de máquinas Debian via SSH**, monta inventário de versões e gera relatório auditável — sem sentar em cada estação.

`Paramiko` · `Relatórios CSV/TXT` · `Logs de auditoria`

</td>
</tr>
</table>

### 🏗️ ObraFácil — gestão de obras com IA offline

> **TCC · Engenharia de Software · CatólicaSC**

Aplicativo Android para pequenas e médias construtoras trocarem o controle informal — bloco de notas, WhatsApp e memória — por um registro auditável de custos, com fluxo de aprovação entre **mestre de obra** (lança) e **gestor** (aprova).

O diferencial técnico é a **IA rodando 100% no dispositivo**: sem latência, sem custo por requisição e, principalmente, **funcionando sem sinal** — que é a realidade do canteiro.

| O que faz | Como |
|---|---|
| 📄 Lê nota fiscal por foto | OCR via Google ML Kit, on-device |
| 🧱 Reconhece materiais | Image labeling, on-device |
| 🎤 Lança custo por voz | `speech_to_text` + parser próprio de números por extenso |
| 📈 Prevê estouro de orçamento | Regressão local sobre o histórico da obra |
| 📸 Estima progresso da obra | Análise comparativa de imagens |
| 📊 Gera relatório semanal | Sumarização automática dos lançamentos |

<div align="center">

`Flutter` · `Firebase` · `ML Kit` · `Provider` · `go_router` · `fl_chart`

**75** arquivos Dart &nbsp;•&nbsp; **~14.4k** linhas &nbsp;•&nbsp; **98** testes passando &nbsp;•&nbsp; **11** serviços de IA &nbsp;•&nbsp; **CI** com build de APK

</div>

Arquitetura **offline-first**: a persistência do Firestore garante que o app opere sem rede e sincronize sozinho quando o sinal volta. As rotinas de background (`workmanager`) checam aprovações pendentes e alertas de estoque mesmo com o app fechado.

<br>

### 🐧 linux-system-updater — automação de parque Debian

> ⚠️ Versão de demonstração — o sistema em produção é confidencial

Dupla de ferramentas em Python que elimina o trabalho de atualizar máquina por máquina:

**`Computadores.py`** — varre a rede, identifica as máquinas Linux acessíveis via SSH e monta um inventário de versões (Debian, Chrome/Chromium, Firefox ESR), exportando em **CSV e TXT**. Também distribui e executa o payload de atualização remotamente.

**`Atualizador.py`** — executa `apt update`, `upgrade` e `dist-upgrade` em modo não-interativo, com **tratamento de erro** para as falhas clássicas do apt e **log detalhado para auditoria**.

<div align="center">

`Python 3` · `Paramiko/SSH` · `Debian` · `Credenciais via env vars`

</div>

Todo dado sensível — usuário, senha, IPs internos, caminhos — foi removido e substituído por variáveis de ambiente (`SSH_USER`, `SSH_PASS`, `TARGET_IPS`), justamente para o repositório público não expor a topologia da infraestrutura real.

<br>

### 🌐 Sistema-n3 — full-stack acadêmico

Aplicação dividida em `backend` (Java + Maven) e `frontend` (JavaScript, HTML, CSS), feita para exercitar a separação entre API e cliente.

---

## 🛠️ Stack Tecnológica

<div align="center">

**Uso no dia a dia**

<img align="center" alt="Python" height="45" width="55" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg">
<img align="center" alt="Shell" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg"/>
<img align="center" alt="Linux" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/linux/linux-original.svg"/>
<img align="center" alt="Debian" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/debian/debian-original.svg"/>
<img align="center" alt="Flutter" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/flutter/flutter-original.svg" />
<img align="center" alt="Dart" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/dart/dart-original.svg" />
<img align="center" alt="Firebase" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/firebase/firebase-plain.svg" />

**Banco de dados & Web**

<img align="center" alt="MariaDB" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mariadb/mariadb-original.svg" />
<img align="center" alt="MySQL" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg">
<img align="center" alt="SQLite" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sqlite/sqlite-original.svg">
<img align="center" alt="JavaScript" height="45" width="55" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
<img align="center" alt="Java" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg">
<img align="center" alt="HTML5" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg">
<img align="center" alt="CSS3" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg">

**Também trabalho com**

<img align="center" alt="Go" height="45" width="55" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/go/go-original-wordmark.svg">
<img align="center" alt="C" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/c/c-original.svg" />
<img align="center" alt="C++" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/cplusplus/cplusplus-original.svg" />
<img align="center" alt="Git" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" />
<img align="center" alt="GitHub Actions" height="45" width="55" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/githubactions/githubactions-original.svg" />

<br><br>

<img alt="Debian" src="https://img.shields.io/badge/Linux-Debian_13-A81D33?style=for-the-badge&logo=debian&logoColor=white">
<img alt="Automação" src="https://img.shields.io/badge/Infra-Automation-0052CC?style=for-the-badge&logo=gnubash&logoColor=white">
<img alt="Redes" src="https://img.shields.io/badge/Redes-SNMP_·_LLDP-16A34A?style=for-the-badge&logo=cisco&logoColor=white">

</div>

---

## 📊 GitHub

<div align="center">

<img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=LucasMueller134&theme=dracula" alt="Resumo do perfil" />

<br>

<img height="200em" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=LucasMueller134&theme=dracula" alt="Linguagens por repositório" />
<img height="200em" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=LucasMueller134&theme=dracula" alt="Linguagens por commit" />

<br>

<img height="200em" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=LucasMueller134&theme=dracula" alt="Estatísticas gerais" />
<img height="200em" src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=LucasMueller134&theme=dracula&utcOffset=-3" alt="Horários mais produtivos" />

<br><br>

<img src="https://streak-stats.demolab.com?user=LucasMueller134&theme=dracula&hide_border=true&locale=pt_BR&date_format=j%20M%5B%20Y%5D" alt="Sequência de contribuições" />

</div>

---

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/LucasMueller134/LucasMueller134/output/pacman-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/LucasMueller134/LucasMueller134/output/pacman-contribution-graph.svg">
  <img alt="Gráfico de contribuições estilo Pac-Man" src="https://raw.githubusercontent.com/LucasMueller134/LucasMueller134/output/pacman-contribution-graph.svg">
</picture>

</div>

---

<div align="center">

### 📫 Vamos conversar

<a href="mailto:lucas134cell@gmail.com">
  <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
</a>
<a href="https://www.linkedin.com/in/lucas-mueller-ab1b1624a" target="_blank">
  <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
</a>
<a href="https://github.com/LucasMueller134">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</a>

<br><br>

<i>"Se eu fiz duas vezes na mão, na terceira vira código."</i>

</div>
