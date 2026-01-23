# Programación y Plataformas Web

*Sebastian Cabrera*
📧 ccabreram1@est.ups.edu.ec 
💻 GitHub: [Sebastian Cabrera](https://github.com/Ccabreram1)

---
## 📊 9. Resultados y Evidencias Requeridas

La carga masiva se ejecutó exitosamente y se comprobó el correcto funcionamiento de las relaciones N:N, cumpliendo con todos los requisitos planteados.

---

### **9.1. Datos para revisión**

**Usar un dataset de al menos 1000 productos**:
Crear un script de carga masiva para poblar la base de datos con datos variados:
- al menos 5 usuarios
- alemnos 2 categorias por producto  
- Precios variados ($10 - $5000)
- Nombres con texto buscable

---

### **9.2. Evidencias de funcionamiento** Caputuras de Postman
1. **Page response**: `GET /api/products?page=0&size=5` mostrando metadatos completos
![PageResponse](assets/PageResponse.png)
2. **Slice response**: `GET /api/products/slice?page=0&size=5` sin totalElements
![SliceResponse](assets/SliceResponse.png)
3. **Filtros + paginación**: `GET /api/products/search?name=laptop&page=0&size=3`
![FitrosPaginacion](assets/FiltrosPaginación.png)
4. **Ordenamiento**: `GET /api/products?sort=price,desc&page=1&size=5`
![Ordenamiento](assets/Ordenamiento.png)
---

### **9.3. Evidencias de performance**
1. **Comparación**: Tiempos de respuesta Page vs Slice

**Consultas de prueba con volumen**: para cada uno Page y Slice
1. Primera página de productos (page=0, size=10)
![Page](assets/PrimeraPagina.png)
![Slice](assets/PrimeraPaginaSlice.png)
2. Página intermedia (page=5, size=10) 
![Page](assets/PaginaIntermedia.png)
![Slice](assets/PaginaIntermediaSlice.png)
3. Últimas páginas para verificar performance
![Page](assets/PerformancePaginado.png)
![Slice](assets/performanceSlice.png)
4. Búsquedas con pocos y muchos resultados
![Pocos](assets/SearchPocos.png)
![Muchos](assets/SearchMuchos.png)
5. Ordenamiento por diferentes campos
![Ordenamiento](assets/Ordenamiento.png)

# Modulo 11

## 1. login
![Login](assets/Login.jpeg)

## 2. register
![Register](assets/Registrar.jpeg)

## 3. api/users SIN TOKEN 
![api/users](assets/SinToken.jpeg)
