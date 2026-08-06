# Labs de Segurança Básica

Arquivos JSON para importar no **Simulador de Topologia de Rede**.  
Cada lab planta **falhas de segurança** (senhas, Wi-Fi, firewall, atualizações) para a turma diagnosticar e corrigir.

## Como o aluno usa

1. Abra o simulador (`simulador-topologia-rede.html`).
2. Clique em **⬆ Importar** e escolha um arquivo desta pasta.
3. Clique em **🔒 Segurança** (ou **Auditar** no painel lateral).
4. Corrija as falhas em **vermelho** nos dispositivos (painel de propriedades → bloco 🔒 Segurança).
5. Clique de novo em **🔒 Segurança** até o badge ficar **OK**.

### Sequência de aula: duas redes + invasão + firewall

Ideia: a turma monta (ou importa) **duas redes completas** ligadas pelo **ISP**. Os PCs têm arquivo secreto e começam **sem firewall**.

1. **Montar a rede** — Site A e Site B com host, switch, roteador, IPs e cabos (ou importe `04-duas-redes-invasao.json`).
2. **Arquivo secreto** — no host, nome + conteúdo (no lab 04 já vem pronto) e **Salvar**.
3. **1º teste de invasão** (professor) — **🎯 Teste de invasão** → host alvo → **sucesso do ataque** (vermelho) porque o firewall está OFF.
4. **Proteger** — aluno marca **Firewall do host ativo**, salva (opcional: firewall do roteador também).
5. **2º teste de invasão** — mesmo host → **ataque bloqueado** (verde). Rede resiste.
6. **Discutir** — o que o firewall faz; diferença host vs roteador; demais itens de 🔒 Segurança.

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
