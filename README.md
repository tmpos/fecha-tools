# fecha-tools
🪜 PASO 1 — Crear el repositorio en GitHub

Entra a 👉 https://github.com/new

Completa los campos así:

Repository name: fecha-tools

Description:
Utilidad profesional de fechas desarrollada por TM POS SRL — compatible con Vue, Electron y Node

Visibility:
Pública (si quieres compartirla) o privada (si es solo para tus sistemas)

Marca ✅ “Add a README file”

Opcional: selecciona .gitignore → “Node”

No agregues licencia todavía (la pondremos después con tu marca)

Dale clic en Create repository.

🪜 PASO 2 — Clonar el repositorio en tu PC

Abre una terminal (o Git Bash) en la carpeta donde trabajas tus proyectos, y ejecuta:

git clone https://github.com/<tu_usuario>/fecha-tools.git


Ejemplo:

git clone https://github.com/TMPOSRD/fecha-tools.git


Luego entra a la carpeta:

cd fecha-tools

🪜 PASO 3 — Crea la estructura del proyecto

Dentro de la carpeta, crea estos archivos:

fecha-tools/
│
├── src/
│   └── fechaTools.js       ← (el archivo principal que ya tenemos)
│
├── README.md               ← (la documentación que te di)
├── package.json            ← (lo crearemos ahora)
└── .gitignore

🪜 PASO 4 — Crear el package.json

En la terminal, ejecuta:

npm init -y


Esto creará un package.json básico.
Luego edítalo para dejarlo bonito, así:

{
  "name": "fecha-tools",
  "version": "3.0.0",
  "description": "Utilidad profesional de fechas desarrollada por TM POS SRL, compatible con Vue, Electron, Node y Capacitor.",
  "main": "src/fechaTools.js",
  "keywords": [
    "tmpos",
    "fecha",
    "date",
    "electron",
    "vue",
    "capacitor",
    "moment",
    "utilidad"
  ],
  "author": "Tomás de Jesús Taveras Jiménez <soporte@tmposrd.com>",
  "license": "TM POS SRL INTERNAL LICENSE"
}

🪜 PASO 5 — Copiar los archivos

Crea la carpeta src

Dentro de ella, pega el archivo completo que ya te generé: fechaTools.js

Copia el README.md que hicimos (puedes pegarlo tal cual)

🪜 PASO 6 — Verificar y hacer el primer commit

Ejecuta en la terminal:

git add .
git commit -m "✨ Versión inicial de fechaTools.js - TM POS SRL"
git push origin main


👉 Esto sube todo a GitHub.

🪜 PASO 7 — Prueba rápida en Node

Para confirmar que funciona, ejecuta:

node


Luego pega:

import { FechaTools } from './src/fechaTools.js';
console.log(FechaTools.nfecha('fechaAmericana'));


Si te devuelve la fecha actual, ¡todo está perfecto! 🎯

¿Quieres que ahora te prepare el .gitignore, la licencia TM POS SRL personalizada,
y el fechaTools.d.ts (para que VS Code te autocomplete todo)?
Podemos hacerlo como siguiente paso antes de publicar la versión 3.0.0 oficial del repositorio.

Tú dijiste:
si pero quiero el readme con las instrucciones con toda la documentacion
ChatGPT Plus

Perfecto 💪🔥
vamos a dejarlo profesional y completo,
con todo lo que incluye documentación, instalación, ejemplos, comandos, estructura del repositorio y notas técnicas,
para que tu proyecto fecha-tools se vea como una librería de nivel empresarial de TM POS SRL.

🗓️ fecha-tools.js – Utilidad profesional de fechas (by TM POS SRL)

Versión: 3.0.0
Autor: Tomás de Jesús Taveras Jiménez

Empresa: TM POS SRL
Correo: soporte@tmposrd.com

Compatibilidad: Vue 3 / Electron / Node / Capacitor / Express
Licencia: TM POS SRL Internal License

📘 Descripción general

fecha-tools es una utilidad avanzada desarrollada por TM POS SRL
para el manejo profesional de fechas y tiempos en sistemas empresariales.
Está diseñada para integrarse de forma nativa con proyectos hechos en Vue 3, Electron, NodeJS o Capacitor,
y proporciona una amplia colección de funciones listas para:

📅 Generar fechas dinámicas y rangos de tiempo

📈 Calcular diferencias, porcentajes y métricas

🧾 Formatear fechas en lenguaje humano o técnico

🕓 Crear encabezados de reportes y balances automáticos

🌎 Trabajar con idioma, formato y zona horaria personalizados

Inspirada en librerías como Moment.js y Day.js,
pero ligera, moderna y adaptada a las necesidades de los sistemas TM POS.

📂 Estructura del repositorio
fecha-tools/
│
├── src/
│   └── fechaTools.js       # Archivo principal con todas las funciones
│
├── README.md               # Documentación completa
├── package.json            # Configuración del módulo NPM
├── .gitignore              # Archivos ignorados por Git
└── LICENSE.md              # Licencia interna TM POS SRL

⚙️ Instalación
🔹 Opción 1 — Clonando desde GitHub
git clone https://github.com/TMPOSRD/fecha-tools.git
cd fecha-tools

🔹 Opción 2 — Usando NPM (opcional, si lo publicas)
npm install fecha-tools

🧩 Uso básico

Importa la librería:

import { FechaTools } from "@/funciones/fechaTools.js";


Obtén la fecha actual:

console.log(FechaTools.nfecha("fecha"));            // "05/10/2025"
console.log(FechaTools.nfecha("fechaAmericana"));   // "2025-10-05"
console.log(FechaTools.nfecha("hora"));             // "1:45:12 pm"

🗓️ Rangos predefinidos
Pedido	Descripción	Ejemplo
"ultimos3dias"	Últimos 3 días	{ fechainicio: "2025-10-02", fechafin: "2025-10-05" }
"ultimos7dias"	Últimos 7 días	{ ... }
"ultimos15dias"	Últimos 15 días	{ ... }
"ultimos30dias"	Últimos 30 días	{ ... }
"ultimos60dias"	Últimos 60 días	{ ... }
"ultimos90dias"	Últimos 90 días	{ ... }
"mestimestamp"	Desde inicio del mes hasta ahora	{ ... }
"anioActual"	Año actual (enero a diciembre)	{ ... }
"anioAnterior"	Año anterior completo	{ ... }
"trimestreActual"	Trimestre en curso	{ ... }
"semestreActual"	Semestre actual	{ ... }
📆 Fechas específicas
Pedido	Resultado
"fechaManana"	"06/10/2025"
"fechaAyer"	"04/10/2025"
"fechaAnteayer"	"03/10/2025"
"fechaPasadoManana"	"07/10/2025"
"horaAmericana"	"13:42:05"
"timestamp"	"2025-10-05 13:42:05"
🧮 Funciones de cálculo
FechaTools.diasEntre("2025-10-01", "2025-10-05"); // 4
FechaTools.mesesEntre("2025-01-01", "2025-10-01"); // 9
FechaTools.esFinDeSemana("2025-10-05"); // true
FechaTools.esDiaHabil("2025-10-03"); // true
FechaTools.porcentajeMes(); // 16 (porcentaje transcurrido)
FechaTools.diasRestantesMes(); // 26

🧠 Formato humano

Transforma cualquier fecha a un texto legible:

FechaTools.formatoHumano("2025-10-05 14:30:00", "es");
// "Domingo 5 de Octubre de 2025, 2:30 pm"


En inglés:

FechaTools.formatoHumano("2025-10-05", "en");
// "Sunday, October 5, 2025"

🕓 Detalles completos de una fecha
FechaTools.nfecha("detalles", { fecha: "2025-08-22 14:00:00" });


Devuelve:

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

🧾 Encabezado de reportes / tickets
FechaTools.nfecha("encabezadoPDF");


Resultado:

{
  "fechaLarga": "Domingo 5 de Octubre de 2025, 1:45 pm",
  "rangoMes": "01/10/2025 al 05/10/2025",
  "textoMes": "Octubre 2025"
}


Perfecto para incluir en:

Reportes PDF

Balances de caja

Tickets de pago

Facturas automáticas

⚙️ Funciones disponibles
FechaTools = {
  nfecha,                // Función principal
  diasEntre,             // Días entre dos fechas
  mesesEntre,            // Meses entre dos fechas
  esFinDeSemana,         // Sábado o domingo
  esDiaHabil,            // Lunes a viernes
  porcentajeMes,         // % del mes transcurrido
  diasRestantesMes,      // Días restantes del mes
  formatoHumano,         // Fecha larga y legible
  detalles,              // Info completa de una fecha
  rangoTrimestre,        // Rangos trimestrales
  rangoSemestre          // Rangos semestrales
};

🧾 Ejemplo práctico con Vue 3
import { FechaTools } from "@/funciones/fechaTools.js";

const rango = FechaTools.nfecha("ultimos30dias");
console.log("Filtrando desde:", rango.fechainicio, "hasta:", rango.fechafin);

const encabezado = FechaTools.nfecha("encabezadoPDF");
console.log("Generando reporte:", encabezado.fechaLarga);

🧠 Modo debug

Si quieres ver todos los cálculos internos:

FechaTools.nfecha("debug");


📤 Muestra en consola:

Día actual y hora

Rangos calculados (semana, mes, trimestre)

Fechas clave

Porcentajes y métricas

🧩 Rangos por trimestre y semestre
Pedido	Descripción
"trimestreActual"	Rango del trimestre en curso
"trimestreAnterior"	Trimestre anterior completo
"semestreActual"	Enero–Junio o Julio–Diciembre
"semestreAnterior"	Semestre anterior completo
🧭 Soporte de idioma y zona horaria

Puedes definir idioma o zona:

FechaTools.nfecha("formatoHumano", { fecha: "2025-10-05", idioma: "en" });


Idiomas disponibles:

"es" → Español

"en" → Inglés

🧰 Comandos útiles
Inicializar el proyecto
npm init -y

Agregar todos los cambios
git add .

Crear commit
git commit -m "✨ Versión inicial de fecha-tools 3.0.0 - TM POS SRL"

Subir al repositorio
git push origin main

🧾 Licencia TM POS SRL

Este software es de uso interno de TM POS SRL
y sus proyectos derivados (TM POS, TM PRÉSTAMOS, TM GYM, etc.)
No puede ser distribuido, modificado ni vendido sin autorización escrita.
© 2025 TM POS SRL – Todos los derechos reservados.

👨‍💻 Autor

Tomás de Jesús Taveras Jiménez
Programador Fullstack – Fundador de TM POS SRL
📧 soporte@tmposrd.com

🌎 https://tmposrd.com

📍 República Dominicana
