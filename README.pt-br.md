<div align="center">

# 🎮 Resgatando The DeadZone

**Um servidor privado para The Last Stand: Dead Zone**

[![Discord](https://img.shields.io/discord/YOUR_DISCORD_ID?color=7289da&logo=discord&logoColor=white)](https://discord.gg/jFyAePxDBJ)
[![Java](https://img.shields.io/badge/Java-25-orange.svg)](https://www.oracle.com/java/technologies/downloads)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.0-purple.svg)](https://kotlinlang.org/)
[![MariaDB](https://img.shields.io/badge/MariaDB-11+-blue.svg)](https://mariadb.org/)

</div>
<div align="center">

[![en](https://img.shields.io/badge/lang-en-red.svg)](./README.md)
[![fr](https://img.shields.io/badge/lang-fr-yellow.svg)](./README.fr.md)
[![pt-br](https://img.shields.io/badge/lang-pt--br-green.svg)](./README.pt-br.md)

</div>


---

## 📖 About

Resgatando The Dead Zone é um projeto de revitalização da comunidade para The Last Stand: Dead Zone. Este servidor privado permite aos jogadores reviver a experiência do jogo original com uma infraestrutura moderna desenvolvida em Kotlin.

> **⚠️ Aviso:** Observação: Este é um projeto não oficial. Todos os direitos sobre The Last Stand: Dead Zone são propriedade exclusiva da Con Artist Games, que nos concedeu permissão para este projeto.

> **⚠️ Aviso de segurança:** Este projeto utiliza versões desatualizadas do Kotlin que podem conter vulnerabilidades de segurança conhecidas e não deve ser usado em produção. O código em si é seguro e pode ser executado localmente.

Esta versão foi originalmente lançada pela Dead Zone Revive e está hospedada aqui para fins de preservação. Se você tem interesse no projeto, sinta-se à vontade para contribuir!

> 📚 Consulte [ARCHITECTURE.md](./ARCHITECTURE.md) para mais detalhes.

## 📋 Pré-requisitos

- **Java 25** or maior - [Download](https://www.oracle.com/java/technologies/downloads)
- **MariaDB 11+** - [Guia de Instalação](https://mariadb.org/download/)
- **Gradle** (incluso via wrapper)

## 🚀 Instação

### 1. Configure o banco de dados

```sql
CREATE DATABASE prod_deadzone_game;
```

As tabelas vão ser criadas automaticamente quando o servidor for iniciado pela primeira vez.

### 2. Configure o Servidor

Crie o arquivo `src/main/resources/application.yaml` a partir do template:

```bash
cp src/main/resources/application.yaml.example src/main/resources/application.yaml
```

Então modifique suas configurações:

```yaml
maria:
  url: jdbc:mariadb://localhost:3306/prod_deadzone_game
  user: root
  password: ""

game:
  host: 127.0.0.1
  port: 7777
```

> **Aviso:** O arquivo `application.yaml` contém informações sensíveis e não deve ser commitado. Ele é ignorado pelo `.gitignore`.

### 3. Compile o projeto

**Windows:**
```bash
build.bat
```

**Linux/macOS:**
```bash
chmod +x build.sh
./build.sh
```

### 4. Inicie o Servidor

**Modo de produção (a partir da pasta `deploy`):**
```bash
# Windows
autorun.bat

# Linux/macOS
./autorun.sh
```

**Modo de desenvolvimento:**
```bash
./gradlew run
```

O servidor estará acessível em:
- **HTTP API:** `http://127.0.0.1:8080`
- **Game Socket:** `127.0.0.1:7777`
- **Broadcast:** Portas `2121-2123`
- **Flash Policy:** Portas `843`

### 5. (Opcional) Abra o Jogo

Se necessário você pode utilizar o [Deadzone Dev Launcher](https://github.com/victorgrodriguesm7/deadzone-dev-launcher) para acessar o jogo localmente

## 🔧 Stack Técnica

- **Linguagem:** Kotlin 2.0.21
- **Framework:** Ktor (WebSockets + REST API)
- **Banco de Dados:** MariaDB + Exposed ORM
- **Serialização:** kotlinx.serialization (JSON + ProtoBuf)
- **Build:** Gradle 8.14
- **Arquitetura:** Clean Architecture + Factory Pattern

## 🤝 Contribua

Contribuições são bem vindas! Aqui como participar:

1. Crie um **Fork** do projeto
2. **Crie** um branch para sua feature
```bash
   git checkout -b feature/new-feature
   ```
3. **Comite** suas mudanças
```bash
  git commit -m “Adicionando uma nova feature”
  ```
4. **Push** para sua branch
```bash
  git push origin feature/new-feature
  ```
5. **Abra** aum Pull Request

### Diretrizes para contribuições

- Siga as convenções padrão do Kotlin
- Adicione comentários claros para funções importantes
- Teste suas alterações antes de enviá-las
- Documente novos recursos

## 📚 Documentação

### Arquitetura do Projeto

Para uma compreensão aprofundada da arquitetura, consulte:

📖 **[ARCHITECTURE.md](./ARCHITECTURE.md)** - Documentação Completa:
- Estrutura detalhada do projeto
- Fluxo de comunicação cliente/servidor
- Principais componentes e serviços
- Tipos de mensagens (mais de 100 tipos)
- Guia de desenvolvimento

### Documentação Externa

Documentação completa disponível em um repositório dedicado:

🔗 [Documentação do DeadZone](https://github.com/glennhenry/DeadZone-Documentation)

## 💬 Community

- **Discord:** [Entre no Servidor](https://discord.gg/jFyAePxDBJ)
- **Issues:** [Relatar um Erro](https://github.com/SulivanM/Sandbox-DZ/issues)
- **Discussions:** Compartilhe suas ideias e obtenha ajuda

## 📝 Licença

Este projeto é um esforço comunitário de revitalização. Todos os direitos de The Last Stand: Dead Zone pertencem à Con Artist Games.

---

<div align="center">

Desenvolvido com ❤️ pela comunidade de DeadZone

[Discord](https://discord.gg/jFyAePxDBJ) • [Website](https://github.com/SwitchCompagnie/Deadzone-Revive-Website-Game)

</div>