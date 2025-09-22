<header>
  
# Shader URP M.A.S.

![Screenshot_1](https://github.com/user-attachments/assets/f93f22be-358d-40f6-a7fe-5beb27589b9d)

### C:\Users\Jairo\Documents\Adobe\Adobe Substance 3D Painter\assets\export-presets





Shader para UNity URP 
Sistema MAS /MASAE: Se extraerán 3 texturas por material, (4 si este tiene emisivo)
Textura 1 - MainTex , canales RGB, A si tiene opacidad (MASAE)
Textura 2 - M.A.S.
   - M: Metallic, canal R
   - A: Ambient occlusion, canal G
   - S: Smoothnes, canal B  (Inverso de Roughness).
Textura 3 - Normales, canales RGB
OPCIONAL Textura 4 - Emissive, canales RGB

</header>

## Substance Export Template

C:\Program Files\Adobe\Adobe Substance 3D Painter\resources\starter_assets
Colocar aquí los archivos de ajustes preestablecidos (*.spexp) que se van a utilizar como ajustes preestablecidos de exportación

![Screenshot_2](https://github.com/user-attachments/assets/04e4d969-f9b6-48ff-bdf2-724f9a1f6347)
![Screenshot_3](https://github.com/user-attachments/assets/1aeb12aa-dd70-42aa-806e-e852e9ad1f77)


# Shader URP Lit

<img width="868" height="687" alt="image" src="https://github.com/user-attachments/assets/2e3b75a4-59dd-4c60-849f-2f848b3ea4da" />

🎨 Exportación de texturas para Unity URP/Lit

Este preset de Substance Painter está configurado específicamente para el shader Universal Render Pipeline/Lit (workflow metálico).
Cada material exporta las siguientes texturas:

## ColorAlpha (_BaseMap)

  - RGB: Albedo / Color base
  - A: Opacidad (para materiales con transparencia o alpha clip)
  - Import en Unity: sRGB activado

## MetallicGlossMap (_MetallicGlossMap)

  - R: Metallic
  - A: Smoothness (1 – Roughness)
  - G/B: sin uso
  - Import en Unity: sRGB desactivado
  - En el material Lit: fijar Smoothness Source = Metallic Alpha

## Normal Map (_BumpMap)

  - RGB: Normal map en espacio tangente (DirectX, canal verde no invertido)
  - Import en Unity: marcar como Normal Map (Unity fuerza sRGB off)

## OcclusionMap (_OcclusionMap)

  - G: Ambient Occlusion (Unity lo lee del canal verde)
  - R/B: negro o blanco
  - Import en Unity: sRGB desactivado

## EmissionMap (_EmissionMap) (opcional)

  - RGB: Emisión de color
  - Import en Unity: sRGB activado

# 🔧 Recomendaciones en Unity

  - sRGB ON → Solo en texturas que representan colores visibles (BaseMap, Emission).
  - sRGB OFF → Para texturas de datos (MetallicGloss, Occlusion, Normal).
  - Normal maps: asegúrate de exportarlos como DirectX y marcar el import en Unity como Normal Map.
