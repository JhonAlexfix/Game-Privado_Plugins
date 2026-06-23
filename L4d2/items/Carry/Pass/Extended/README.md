L4D2 Items Carry Pass Extended

------------------------------------------------------------
DESCRIPCIÓN

L4D2 Items Carry Pass Extended es un plugin avanzado para servidores de Left 4 Dead 2 (SourceMod / SourcePawn).

Permite a los supervivientes intercambiar objetos y armas en tiempo real entre jugadores usando interacción directa en el juego.

Incluye sistema de inventario estable, compatibilidad por slots y fix crítico de munición.

------------------------------------------------------------
DEMO

https://youtu.be/3UKS6H8Cspk

------------------------------------------------------------
CARACTERÍSTICAS

- Intercambio de objetos en tiempo real entre jugadores
- Uso de clic derecho como interacción principal
- Sin menús ni comandos
- Intercambio inteligente de armas por slot compatible
- Mantiene estabilidad de inventario
- Fix de munición (v6.1):
  - m_iClip1
  - m_iAmmo
  - ammo reserve
- Modo silencioso (sin mensajes de chat)
- Sistema fácil de expandir (arrays editables)

------------------------------------------------------------
OBJETOS SOPORTADOS

- gascan
- propanetank
- oxygentank
- fireworkcrate
- cola_bottles
- gnome

------------------------------------------------------------
INSTALACIÓN

1. Compilar el plugin:

spcomp l4d2_items_carry_pass_extended.sp

2. Copiar el archivo compilado a:

/addons/sourcemod/plugins/

3. Cargar el plugin en el servidor:

sm plugins load l4d2_items_carry_pass_extended

------------------------------------------------------------
USO

Acción: Clic derecho sobre jugador
Resultado: Transferir objeto o arma

Acción: Sostener item transportable
Resultado: Permite pasar el objeto

Acción: Arma compatible
Resultado: Intercambio automático por slot

------------------------------------------------------------
PERSONALIZACIÓN

Editar array de items:

char g_sCarryableItems[][] =
{
    "gascan",
    "propanetank",
    "oxygentank",
    "fireworkcrate",
    "cola_bottles",
    "gnome",

    "molotov_projectile",
    "item_custom_example"
};

------------------------------------------------------------
COMPATIBILIDAD

- Left 4 Dead 2 (Steam)
- SourceMod 1.11 o superior

------------------------------------------------------------
NOTAS

- Diseñado para server host local o servidores competitivo
- Puede requerir ajustes con otros plugins de inventario
- Recomendado probar en servidor local antes de producción

------------------------------------------------------------
AUTOR

Proyecto privado desarrollado en SourcePawn
Sistema de intercambio de ítems y armas para Left 4 Dead 2