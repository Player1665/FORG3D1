# Roteiro de commits — FORG3D

Sugestão para subir o projeto **aos poucos**, cada um fazendo seus commits, para o histórico do GitHub mostrar o trabalho dos dois. Siga a ordem: cada passo só usa arquivos que já existem nos passos anteriores.

## Preparação (uma vez)

**Diego** cria o repositório e convida o Luan:
1. github.com → **New repository** → nome `FORG3D` → *Create*.
2. *Settings → Collaborators → Add people* → usuário do Luan.

Cada um, no próprio PC (pasta `C:\xampp\htdocs`):
```bash
git config --global user.name  "Seu Nome"
git config --global user.email "seu-email-do-github@exemplo.com"
```

**Diego** (primeiro commit):
```bash
cd C:\xampp\htdocs\FORG3D
git init
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/FORG3D.git
```

**Luan** (depois que o Diego fizer o primeiro push):
```bash
cd C:\xampp\htdocs
git clone https://github.com/SEU-USUARIO/FORG3D.git
```

> Antes de começar cada commit: `git pull`. Depois: `git add ...` → `git commit -m "..."` → `git push`.
> **Nunca** faça `git add` do `processamento/config.php` (o `.gitignore` já bloqueia).

---

## Os commits

Dica: para "liberar" os arquivos aos poucos, copie do ZIP para a pasta do repositório só os arquivos daquele passo.

| # | Quem | Arquivos | Mensagem |
|---|---|---|---|
| 1 | Diego | `README.md`, `.gitignore` | `docs: README e gitignore do projeto` |
| 2 | Luan | `banco/forg3d.sql` | `feat(banco): cria tabelas e dados de exemplo` |
| 3 | Diego | `processamento/config.exemplo.php`, `processamento/funcoesBD.php` | `feat(back): conexão PDO e funções do banco` |
| 4 | Luan | `processamento/sessao.php` | `feat(back): sessão, níveis de acesso e mensagens` |
| 5 | Diego | `css/forg3d.css`, `img/logo.svg` | `style: tema metal forjado e logo FORG3D` |
| 6 | Luan | `view/includes/topo.php`, `view/includes/rodape.php`, `index.php` | `feat(front): topo, menu e rodapé` |
| 7 | Diego | `processamento/processamento.php`, `view/login.php` | `feat: login com banco e logout` |
| 8 | Luan | `view/recuperarSenha.php`, `view/redefinirSenha.php`, `view/perfil.php` | `feat: recuperação e troca de senha` |
| 9 | Diego | `view/cadastroCliente.php`, `view/verCliente.php` | `feat: cadastro e listagem de clientes` |
| 10 | Luan | `view/cadastroMaterial.php`, `view/verMaterial.php` | `feat: cadastro e listagem de materiais` |
| 11 | Diego | `view/cadastroImpressora.php`, `view/verImpressora.php` | `feat: cadastro e listagem de impressoras` |
| 12 | Luan | `view/cadastroModelo.php`, `view/verModelo.php`, `img/modelos/` | `feat: catálogo de modelos com upload de imagem` |
| 13 | Diego | `view/cadastroUsuario.php`, `view/verUsuario.php` | `feat: gestão de usuários (admin)` |
| 14 | Luan | `js/forg3d.js`, `view/orcamento.php` | `feat: orçamento automatizado com cálculo ao vivo` |
| 15 | Diego | `view/verOrcamento.php`, `view/detalheOrcamento.php` | `feat: lista, detalhe e fluxo de status do orçamento` |
| 16 | Luan | `view/estoque.php` | `feat: estoque inteligente com baixa automática` |
| 17 | Diego | `view/home.php`, `view/configuracoes.php` | `feat: dashboard com gráficos e configurações` |
| 18 | Luan | `processamento/ia.php` | `feat(ia): Assistente da Forja com a API do Claude` |
| 19 | Diego | `banco/forg3d_backup.sql`, `docs/` | `chore: backup da base e documentação` |

Exemplo de um commit (passo 2, Luan):
```bash
git pull
git add banco/forg3d.sql
git commit -m "feat(banco): cria tabelas e dados de exemplo"
git push
```

Observação: entre os passos o sistema pode ficar "quebrado" (um arquivo chama outro que ainda não subiu). Isso é normal no histórico; ao final do passo 19 tudo funciona.
