# workflows

---

## sync-env-repo.yaml

Este flujo de trabajo, llamado "Sync Environment repository", se encarga de crear distintos environment basado en lo que existe dentro del archivo `sync-env-repo.yaml`.

---

## sync-secrets-back.yaml

"Secret Back Sync Environment" permite sincronizar los secretos entre diferentes entornos de desarrollo en GitHub. Este flujo de trabajo se dispara manualmente con la opción workflow_dispatch.

Los entornos y secretos deben existir previamente en el repositorio origen 'orange-templates' para poder ser sincronizados cuando se realiza una llamada POST a la API de GitHub.

### Jobs

1. `sync-dev`: Sincroniza los secretos al entorno de desarrollo. Se ejecuta si el input environment es igual a 'dev'.
2. `sync-qa`: Sincroniza los secretos al entorno de control de calidad. Se ejecuta si el input environment es igual a 'qa'.
3. `sync-prod`: Sincroniza los secretos al entorno de producción. Se ejecuta si el input environment es igual a 'prod'.