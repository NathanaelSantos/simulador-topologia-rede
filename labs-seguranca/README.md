# Labs de Segurança Básica

Arquivos JSON para importar no **Simulador de Topologia de Rede**.  
Cada lab planta **falhas de segurança** (senhas, Wi-Fi, firewall, atualizações) para a turma diagnosticar e corrigir.

## Como o aluno usa

1. Abra o simulador (`simulador-topologia-rede.html`).
2. Clique em **⬆ Importar** e escolha um arquivo desta pasta.
3. Clique em **🔒 Segurança** (ou **Auditar** no painel lateral).
4. Corrija as falhas em **vermelho** nos dispositivos (painel de propriedades → bloco 🔒 Segurança).
5. Clique de novo em **🔒 Segurança** até o badge ficar **OK**.

### Sequência de aula: rede da turma + invasão + firewall

O teste **não depende de um lab fixo**: vale para **qualquer topologia** criada no simulador (1 LAN, 2 sites + ISP, etc.).

1. **Montar a rede** — alunos criam do zero **ou** importam um JSON (ex.: `04-duas-redes-invasao.json`).
2. **Arquivo secreto** — em cada Host: nome + conteúdo (ou no diálogo de invasão: **📄 Preparar arquivo secreto**) e **Salvar**. Firewall começa **OFF**.
3. **1º teste** — **🎯 Teste de invasão** → host alvo → **sucesso do ataque** (vermelho).
4. **Proteger** — ☑ **Firewall do host ativo** → Salvar.
5. **2º teste** — mesmo host → **bloqueado** (verde).
6. **Auditar** — 🔒 Segurança / relatório (senhas, Wi-Fi, updates…).

> Entregue só os JSON + este README. O gabarito fica com o professor (`gabarito/`).

## Checklist (segurança básica)

| Tema | O que o auditor exige |
|------|------------------------|
| **Senhas seguras** | ≥ 8 caracteres, letras + números; sem senhas comuns (`admin`, `123456`…) |
| **Proteção do Wi-Fi** | Se o Wi-Fi estiver ligado: senha forte |
| **WPA / WPA2 / WPA3** | Aberto e WEP = falha; WPA = aviso; WPA2/WPA3 = ok |
| **Atualização** | Hosts e roteadores com atualizações ativas |
| **Firewall** | Firewall do host e do roteador ativos |
| **Wi-Fi públicas** | Host **não** deve permitir redes Wi-Fi públicas |
| **Proteção dos equipamentos** | Senha forte de admin no roteador; admin remota com cuidado |

## Labs

| Arquivo | Tema | Dificuldade |
|---------|------|-------------|
| `01-rede-insegura.json` | Várias falhas de uma vez (senhas, Wi-Fi aberto, firewall off…) | ★★☆ |
| `02-wifi-obsoleto.json` | Wi-Fi com WEP e senha fraca | ★☆☆ |
| `03-hosts-desprotegidos.json` | Hosts sem senha, sem firewall, Wi-Fi pública liberada | ★☆☆ |
| `04-duas-redes-invasao.json` | **Duas redes + ISP + invasão** (firewall OFF → falha → ON → bloqueia) | ★★☆ |

## Sugestão de aula (40–50 min) — foco firewall

1. **10 min** — Conceito: “como proteger a rede planejada?”  
2. **10 min** — Importar `04` (ou montar 2 sites + ISP)  
3. **10 min** — 1º **Teste de invasão** (falha sem firewall)  
4. **10 min** — Ligar firewall no host → 2º teste (sucesso da defesa)  
5. **5–10 min** — Auditar 🔒 Segurança e exportar relatório OK  

## Critério de sucesso

- Painel **Segurança** com badge **OK** (sem falhas vermelhas)  
- Avisos amarelos (ex.: admin remota ligada) podem ser aceitos se o professor permitir  
- Validação de IP (✔ Validar) também deve estar consistente se a topologia tiver endereçamento
