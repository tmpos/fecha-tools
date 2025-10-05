# fecha-tools
📚 Documentación de uso – fecha-tools.js
🧩 Importación del módulo
🔹 En proyectos con ES Modules (Vite, Vue, Electron, Capacitor)
import { FechaTools } from "@/funciones/fechaTools.js";

🔹 En Node.js puro (v18+ con "type": "module")
import { FechaTools } from "./src/fechaTools.js";

🔹 En CommonJS (Node antiguo)
const { FechaTools } = require("./src/fechaTools.js");

⚙️ Uso básico
console.log(FechaTools.nfecha("fecha"));            // "05/10/2025"
console.log(FechaTools.nfecha("fechaAmericana"));   // "2025-10-05"
console.log(FechaTools.nfecha("hora"));             // "1:45:12 pm"
console.log(FechaTools.nfecha("timestamp"));        // "2025-10-05 13:45:12"


✅ La función nfecha() es el núcleo principal.
Recibe un parámetro pedido (el tipo de fecha o rango que quieres)
y devuelve un valor o un objeto { fechainicio, fechafin }.

🗓️ Rangos automáticos listos para reportes
FechaTools.nfecha("ultimos7dias");
FechaTools.nfecha("ultimos15dias");
FechaTools.nfecha("ultimos30dias");
FechaTools.nfecha("mestimestamp");
FechaTools.nfecha("anioActual");
FechaTools.nfecha("anioAnterior");
FechaTools.nfecha("trimestreActual");
FechaTools.nfecha("semestreActual");


📤 Resultado típico:

{
  "fechainicio": "2025-09-05 00:00:00",
  "fechafin": "2025-10-05 23:59:59"
}


Puedes usarlos directamente en consultas SQL, reportes PDF o gráficos de estadísticas.

📅 Fechas específicas
FechaTools.nfecha("fechaManana");          // "06/10/2025"
FechaTools.nfecha("fechaAyer");            // "04/10/2025"
FechaTools.nfecha("fechaAnteayer");        // "03/10/2025"
FechaTools.nfecha("fechaPasadoManana");    // "07/10/2025"
FechaTools.nfecha("horaAmericana");        // "13:45:12"
FechaTools.nfecha("diasemana");            // "Domingo"
FechaTools.nfecha("mesletra");             // "Octubre"

📊 Cálculos y métricas
FechaTools.diasEntre("2025-10-01", "2025-10-05");  // 4
FechaTools.mesesEntre("2025-01-01", "2025-10-01"); // 9
FechaTools.porcentajeMes();                        // 16 (porcentaje del mes transcurrido)
FechaTools.diasRestantesMes();                     // 26 (días que faltan)


Verificación de días hábiles o fines de semana:

FechaTools.esFinDeSemana("2025-10-05"); // true
FechaTools.esDiaHabil("2025-10-03");    // true

🧠 Formato humano / legible

Convierte cualquier fecha en una descripción natural:

FechaTools.formatoHumano("2025-10-05 14:30:00", "es");
// "Domingo 5 de Octubre de 2025, 2:30 pm"

FechaTools.formatoHumano("2025-10-05", "en");
// "Sunday, October 5, 2025"


🗣️ Idiomas disponibles:

"es" → Español

"en" → Inglés

🧾 Encabezado para reportes PDF o tickets
FechaTools.nfecha("encabezadoPDF");


📄 Resultado:

{
  "fechaLarga": "Domingo 5 de Octubre de 2025, 1:45 pm",
  "rangoMes": "01/10/2025 al 05/10/2025",
  "textoMes": "Octubre 2025"
}


Ideal para:

Reportes de ventas o préstamos

Balances de caja

Resúmenes diarios o mensuales

Tickets térmicos

🧩 Detalles completos de una fecha
FechaTools.nfecha("detalles", { fecha: "2025-08-22 14:00:00" });


📦 Resultado:

{
  "dia": "Viernes",
  "numeroDia": "22",
  "mes": "Agosto",
  "numeroMes": "08",
  "year": 2025,
  "hora12": "2:00 pm",
  "hora24": "14:00:00",
  "timestampISO": "2025-08-22T14:00:00.000Z",
  "timestampUnix": 1755864000000,
  "semana": 34
}

🧾 Rangos avanzados
Pedido	Descripción
"trimestreActual"	Rango del trimestre en curso
"trimestreAnterior"	Trimestre anterior completo
"semestreActual"	Enero–Junio o Julio–Diciembre
"semestreAnterior"	Semestre anterior completo
"anioActual"	Año actual completo
"anioAnterior"	Año anterior completo
🧭 Modo debug (para desarrolladores)
FechaTools.nfecha("debug");


🪄 Muestra en consola todos los cálculos internos:

Día actual

Rangos (semana, mes, trimestre, semestre)

Porcentajes de progreso

Ideal para verificar filtros o probar en consola de desarrollo.

⚙️ Lista completa de funciones disponibles
FechaTools = {
  nfecha,                // Core principal
  diasEntre,             // Diferencia en días
  mesesEntre,            // Diferencia en meses
  esFinDeSemana,         // Verifica si es fin de semana
  esDiaHabil,            // Verifica si es día laboral
  porcentajeMes,         // % del mes transcurrido
  diasRestantesMes,      // Días restantes
  formatoHumano,         // Fecha legible
  detalles,              // Info completa de una fecha
  rangoTrimestre,        // Trimestres
  rangoSemestre          // Semestres
};

🧾 Ejemplo práctico con Vue 3 + PrimeVue
<script setup>
import { FechaTools } from "@/funciones/fechaTools.js";
import { ref, onMounted } from "vue";

const rango = ref({});
const encabezado = ref({});

onMounted(() => {
  rango.value = FechaTools.nfecha("ultimos30dias");
  encabezado.value = FechaTools.nfecha("encabezadoPDF");
});
</script>

<template>
  <div class="card">
    <h3>📊 Reporte de Ventas</h3>
    <p>Del {{ rango.fechainicio }} al {{ rango.fechafin }}</p>
    <p>Generado el {{ encabezado.fechaLarga }}</p>
  </div>
</template>

🧰 Comandos útiles del proyecto
Comando	Descripción
npm run start	Ejecuta el módulo directamente
npm run minify	Genera la versión minificada en /dist/fechaTools.min.js
npm run test	Ejecuta pruebas básicas (si se agregan)
git add . + git commit -m "mensaje"	Guarda cambios
git push origin main	Sube los cambios al repositorio
🧑‍💻 Soporte técnico

Desarrollado por:
Tomás de Jesús Taveras Jiménez
Programador Fullstack – Fundador de TM POS SRL
📧 soporte@tmposrd.com

🌎 https://tmposrd.com

📍 República Dominicana