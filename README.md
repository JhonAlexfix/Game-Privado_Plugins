L4D2 Items Carry Pass Extended
==============================

Plugin para Left 4 Dead 2 (SourceMod) que permite pasar armas y objetos entre supervivientes mediante clic derecho, incluyendo un sistema corregido de persistencia de munición (clip + reserva).

--------------------------------
CARACTERÍSTICAS
--------------------------------

- Transferencia de armas entre supervivientes con clic derecho
- Intercambio bidireccional de armas (swap completo)
- Transferencia de objetos transportables (gascan, propano, etc.)
- Respeto de distancia máxima entre jugadores
- Cooldown anti-spam por jugador
- Sistema de equipamiento automático en el receptor
- Fix robusto de munición:
  - Conserva m_iClip1 (balas en cargador)
  - Conserva m_iAmmo (munición de reserva)
  - Evita desincronización del HUD
- Protección contra transferencia inválida de objetos carryables

--------------------------------
FIX DE MUNICIÓN (IMPORTANTE)
--------------------------------

Problema original:
Las armas perdían munición de reserva al ser intercambiadas entre jugadores.

Solución implementada:
- Se guarda el estado del arma antes del intercambio:
  - m_iClip1 (balas en cargador)
  - m_iPrimaryAmmoType (tipo de munición)
  - m_iAmmo (munición del jugador)
- Se restaura directamente en el jugador receptor después del equipamiento
- Se elimina la dependencia de m_hOwnerEntity (fuente de bugs y desincronización)

--------------------------------
COMPATIBILIDAD
--------------------------------

- SourceMod 1.11 o superior
- Left 4 Dead 2 únicamente

Requiere:
- sdktools
- sdkhooks
- clientprefs

--------------------------------
USO EN EL JUEGO
--------------------------------

ARMAS:
1. Mira a otro superviviente
2. Presiona clic derecho
3. El arma se transfiere o intercambia automáticamente

OBJETOS:
- Gas can
- Propane tank
- Oxygen tank
- Firework crate
- Cola bottles
- Gnome

--------------------------------
REGLAS DEL SISTEMA
--------------------------------

- Solo supervivientes pueden usar el sistema
- Distancia máxima: 110 units
- Cooldown: 0.5 segundos por jugador
- No permite sobrescribir objetos carryables en el receptor

--------------------------------
ESTRUCTURA DEL PLUGIN
--------------------------------

- OnPlayerRunCmd -> detección de clic derecho
- DoItemPass() -> intercambio de armas
- DoHandObjectPass() -> objetos transportables
- RestoreAmmo() -> restauración de munición
- WeaponDrop / WeaponEquip -> manejo de entidades

--------------------------------
INSTALACIÓN
--------------------------------

1. Compilar el archivo .sp
2. Subir el .smx a:
   addons/sourcemod/plugins/
3. Reiniciar servidor o cambiar mapa

--------------------------------
NOTAS TÉCNICAS
--------------------------------

- Se eliminó el uso de m_hOwnerEntity para evitar bugs de munición
- La restauración de munición se realiza directamente en el jugador receptor
- Compatible con intercambios bidireccionales
- Reduce desincronización del HUD en swaps rápidos

--------------------------------
CHANGELOG
--------------------------------

v6.1 (ammo fix original)
- Fix inicial de munición con m_iClip1 + m_iAmmo

v6.2 (mejorado)
- Eliminado uso de m_hOwnerEntity
- Restauración de munición ligada directamente al jugador
- Mayor estabilidad en intercambios bidireccionales
- Menos riesgo de desincronización del HUD

--------------------------------
LICENCIA
--------------------------------

Uso libre en servidores comunitarios.
No redistribuir versiones modificadas sin crédito.
