# Diario de Trabajo - Grupo 13

| Fecha | Tarea | Participantes | Decisiones | Problemas | Solución | Resultado | Evidencia |
|---|---|---|---|---|---|---|---|
| 2026-10-16 | Preparación de VM, disco LFS y verificación | Miguel Medina | Uso de segundo disco virtual de 30GB con tabla MBR/BIOS (ext4) y versión r13.1-24-systemd del libro. | Faltaban herramientas de compilación y el enlace simbólico de yacc. | Instalación de herramientas vía dnf y creación del script wrapper para yacc. | Anfitrión verificado correctamente con version-check.sh. | `evidencias/parte1/` |
| 2026-10-16 | Solución de arranque en modo de emergencia | Miguel Medina | UUID corregido para el montaje persistente en `/etc/fstab`. | La máquina virtual entró en modo de emergenciaal reiniciar. | El archivo `/etc/fstab` tenía una etiqueta literal `<uuid-de-sdb1>` en lugar del identificador real del disco de LFS. Se ingresó con credenciales de root, se consultó el UUID correcto mediante `blkid /dev/sdb1`, se actualizó el archivo `/etc/fstab` y se reinició con normalidad. | Sistema operativo arrancando correctamente con el punto de montaje `/mnt/lfs` persistente. | `evidencias/parte1/` |
