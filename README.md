# EDA Edificios — Sector Oriente

Dashboard interactivo de **edificios en altura (más de 4 pisos)** del sector oriente
de Santiago, como herramienta de apoyo para la planificación operativa de bomberos.
Cubre las comunas de **Providencia, Las Condes, Vitacura y Lo Barnechea**.

👉 **Ver el dashboard:** abre `index.html` en el navegador (o el link de GitHub Pages,
si está publicado). Es un archivo autocontenido: los datos van embebidos, no requiere
instalar nada. Solo necesita conexión a internet (mapa base y librerías).

## Qué contiene

**Gráficos**
- Edificios por comuna, mix de uso, distribución de altura (nº de pisos).
- Material estructural por comuna y usos de ocupación vulnerable (salud, hotel,
  educación, comercio).
- Tabla resumen por comuna y ranking de edificios más altos.

**Mapa 1 — interactivo**
- Densidad poblacional por manzana (Censo 2024) coloreada por cuantiles.
- Cada edificio como punto (color = uso, tamaño = nº de pisos).
- Zonas de respuesta (primera/segunda máquina) dibujables a mano y exportables.
- Marcador del cuartel. Botón de pantalla completa.

**Mapa 2 — proxy de red seca**
- Edificios ≥5 pisos (los que por altura deberían tener red seca) clasificados por
  año de construcción respecto a un corte normativo seleccionable (1981 / 1992 / 2002):
  anteriores al corte = *probablemente SIN* red seca.
- Modo "colorear por uso" para ver, entre los que probablemente no tienen, cuáles son
  habitacionales, de salud, oficinas, comercio, etc.

## Fuentes de datos

- **SII — Detalle Catastral**: nº de pisos, destino/uso, subterráneo, material, año de
  construcción y superficie por edificio.
- **INE — Censo 2024**: población por manzana → densidad.
- **Overture Maps**: huellas de edificios (capa base).
- **OGUC (DS 47/1992) y RIDAA (DS 50/2002)**: reglas para el proxy de red seca.

## Metodología y supuestos

- **"Edificio" = estructura de más de 4 pisos.**
- El SII registra un rol por unidad (departamentos, estacionamientos, bodegas); los
  edificios se reconstruyen **colapsando las unidades por su rol de Bien Común**.
- **Subterráneo: sí/no** es confiable; el *número* de niveles subterráneos no es
  recuperable desde el SII.
- **Proxy de red seca**: la norma exige red seca desde 5 pisos; se estima "probablemente
  con/sin" según el **año de construcción** vs el corte normativo elegido. Es una
  **estimación para priorizar**, no una certeza jurídica (la red seca ya se exigía antes
  de 2002, así que el corte 2002 sobreestima los "sin").
- La localización por edificio proviene de geocodificación de direcciones (aproximada).

## Aviso

Herramienta de análisis exploratorio. Los proxys (red seca, subterráneos) son
estimaciones a partir de datos públicos y no reemplazan la verificación en terreno ni
los antecedentes oficiales de cada edificio.
