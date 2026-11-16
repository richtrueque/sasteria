# Sastería — v33 Selector de Empresa que sí deja cambiar

BUG REPORTADO (foto):
- En Hoja de medidas, Empresa = caja popular
- Te equivocas, quieres cambiar a otra empresa, aprietas la flechita y NO te salen todas las empresas
- Tienes que borrar toda la empresa para que salga la lista. Muy confuso para vendedoras.

CAUSA:
- Era un <input list="empresas"> + <datalist>. El navegador filtra el datalist con lo que ya escribiste: si dice "caja popular", solo muestra las que contienen ese texto. La flecha no reabre la lista completa.

ARREGLO:
- Empresa ahora es un combobox propio: campo de texto + botón ▼
- Tocar el campo: muestra las que coinciden con lo que escribiste
- Tocar ▼: SIEMPRE muestra TODAS las empresas, aunque ya tengas "caja popular" escrita, para que toques otra y se cambie al instante (y se recalcula el consecutivo)
- Si es empresa nueva, la escribes y sigues, igual que antes
- Área tiene el mismo arreglo (▼ muestra todas las áreas de esa empresa)
- Se mantiene: v32 Orden integra por empresa (todas las fechas), v31 Conjuntos no en PIN, v30 privacidad por vendedora

Cómo probar:
1. Borra carpeta vieja, descomprime, doble clic en index.html
2. Entra, ve a Toma de medidas, escribe caja popular
3. Aprieta ▼ -> debe salir TODA la lista (PATOLOGIA, CAJA POPULAR, etc.), toca otra y debe cambiarse sin borrar nada
4. Vuelve a apretar ▼ -> debe salir otra vez toda la lista
