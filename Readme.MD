# Laboratório Prático: Cloud-init

Receitas `cloud-init` para automatizar a configuração de VMs (Multipass).

| Missão | Arquivo | Resultado esperado |
|---|---|---|
| 1 | `missao1-nginx.yaml` | Nginx com página customizada na porta 80 |
| 2 | `missao2-docker.yaml` | Container `nginxdemos/hello` na porta 8080 |
| 3 | `missao3-grafana.yaml` | Usuário `aluno`, Git, Docker e Grafana na porta 3000 |

## Uso local (quando houver espaço)

```bash
multipass launch -n vm1 --cloud-init missao1-nginx.yaml
multipass info vm1
multipass delete vm1 --purge
```

## Validação automática

O workflow `.github/workflows/validar-yaml.yml` roda a cada push e verifica:
1. Cabeçalho `#cloud-config`
2. Sintaxe YAML (`yamllint`)
3. Schema oficial (`cloud-init schema`)