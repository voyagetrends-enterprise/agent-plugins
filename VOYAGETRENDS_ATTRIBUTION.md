# VoyageTrends LLC — Atribución de Cuenta AWS

**Organización:** voyagetrends-enterprise  
**Marcas:** Digital-Shore · Shore All in One · The Voyage Vault  
**Fecha de fork:** 29 Oct 2026  
**Origen:** Fork de [awslabs/agent-plugins](https://github.com/awslabs/agent-plugins)

## Propósito
Este fork atribuye y configura el marketplace de Agent Plugins for AWS para uso operativo de VoyageTrends LLC. Permite a los agentes de codificación (Claude Code, Cursor, Codex) desplegar y operar infraestructura AWS bajo la cuenta de la LLC.

## Estado actual
- Fork completado bajo `voyagetrends-enterprise/agent-plugins`
- Pendiente: configuración de AWS CLI / OIDC + CodeBuild en la cuenta AWS de VoyageTrends
- Pendiente: instalación de plugins prioritarios en entornos de agentes

## Próximos pasos
1. Configurar AWS CLI con credenciales de la cuenta VoyageTrends (mínimo privilegio).
2. Seguir `docs/ADMINISTRATORS_GUIDE.md` adaptando:
   - GitHubOrg = `voyagetrends-enterprise`
   - GitHubRepo = `agent-plugins`
   - Cuenta y región AWS de VoyageTrends LLC
3. Instalar plugins:
   ```bash
   /plugin marketplace add voyagetrends-enterprise/agent-plugins
   /plugin install deploy-on-aws@agent-plugins-for-aws
   /plugin install aws-serverless@agent-plugins-for-aws
   ```
4. Integrar con `voyagetrends-enterprise/voyagetrends-net-mcp`.

## Seguridad
- No almacenar secrets AWS en el repositorio.
- Usar OIDC + roles IAM para CI.
- Revisar siempre el código generado por agentes antes de deploy.

**Jefe de Operaciones** — VoyageTrends LLC