# Simulador de Topologia de Rede

Simulador didático (estilo Packet Tracer) para montar topologias, configurar IP e testar comunicação entre hosts.

## Recursos

- **Dispositivos:** Host, Switch, Roteador, **Servidor DHCP**
- **Cabos e validações:** conflitos de IP, gateway, máscaras, loops de switch, rotas
- **Simulação de mensagem:** encapsulamento e animação no quadro
- **DHCP:** escopo, range, máscara, gateway, DNS, lease
- **Renovação T1:** na metade do lease o host renova automaticamente (REQUEST → ACK animado)

## Como usar (GitHub Pages)

Abra o site publicado (após ativar o Pages) ou o arquivo `index.html` / `simulador-topologia-rede.html` no navegador.

### Atividade DHCP (sugestão)

1. Monte a LAN: hosts + switch + roteador + servidor DHCP  
2. Configure o IP do roteador (gateway da LAN)  
3. Ligue o **DHCP no mesmo switch** dos hosts  
4. Configure escopo (range, máscara, gateway, DNS, lease)  
5. Nos hosts: modo **DHCP** → **Obter IP**  
6. Para ver a renovação na aula, use lease curto (ex.: `30` ou `40` segundos)  

## Arquivos

| Arquivo | Descrição |
|---------|-----------|
| `index.html` | Entrada do site (GitHub Pages) |
| `simulador-topologia-rede.html` | Simulador completo |
| `imgs/` | Ícones de switch e roteador |

## Desenvolvimento

Basta abrir o HTML no navegador — não precisa de servidor Node para o simulador de topologia.
