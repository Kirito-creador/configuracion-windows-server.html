<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tutorial: Configuración y Administración de Windows Server</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }

        /* Contenedor Principal */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
        }

        /* Encabezado */
        header {
            background-color: #007bff;
            color: white;
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        header .logo {
            font-size: 24px;
            font-weight: bold;
        }

        header nav {
            display: flex;
        }

        header nav a {
            color: white;
            text-decoration: none;
            margin-left: 20px;
            transition: color 0.3s ease;
        }

        header nav a:hover {
            color: #ddd;
        }

        /* Sección Principal */
        .hero-section {
            text-align: center;
            padding: 60px 20px;
        }

        .hero-section h1 {
            font-size: 48px;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .hero-section p {
            font-size: 18px;
            max-width: 800px;
            margin: 0 auto;
            margin-bottom: 30px;
        }

        .hero-section button {
            background-color: #28a745;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            box-shadow: 0 5px 15px rgba(40, 167, 69, 0.3);
        }

        .hero-section button:hover {
            background-color: #218838;
        }

        /* Contenido Principal */
        .content-section {
            padding: 30px 20px;
        }

        .content-section h2 {
            font-size: 32px;
            margin-bottom: 20px;
            color: #007bff;
        }

        .content-section p {
            font-size: 16px;
            line-height: 1.6;
            text-align: justify;
        }

        .content-section ol {
            list-style-type: decimal;
            padding-left: 20px;
        }

        .content-section li {
            margin-bottom: 10px;
        }
        .image-reference {
            text-align: center;
            margin-top: 20px;
        }

        .image-reference img {
            max-width: 100%;
            height: auto;
            border: 1px solid #ddd;
            padding: 5px;
            border-radius: 5px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .image-reference img:hover {
            transform: scale(1.05);
        }

        .image-reference p {
            font-size: 12px;
            color: #666;
            text-align: center;
            margin-top: 5px;
        }

        /* Cajas de Texto Destacadas */
        .highlight-box {
            background-color: #f0f8ff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero-section h1 {
                font-size: 36px;
            }
            .hero-section p {
                font-size: 16px;
            }
            .hero-section button {
                padding: 10px 20px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>

    <div class="container">

        <header>
            <div class="logo">WindowsServerTutorial.com</div>
            <nav>
                <a href="#inicio">Inicio</a>
                <a href="#active-directory">Active Directory</a>
                <a href="#gpo">GPO</a>
            </nav>
        </header>

        <section class="hero-section" id="inicio">
            <h1>Configuración y Administración de Windows Server</h1>
            <p>Aprende a instalar y gestionar Active Directory, configurar políticas de grupo y administrar usuarios y equipos en un entorno de dominio.</p>
            <button><a href="#active-directory" style="color: white; text-decoration: none;">Comenzar Tutorial</a></button>
        </section>

        <section class="content-section" id="active-directory">
            <h2>Instalación y Gestión de Active Directory</h2>
            <p>Active Directory es un servicio centralizado que permite gestionar usuarios, equipos, grupos y recursos en una red corporativa. Proporciona autenticación, autorización y control de acceso.</p>

            <div class="highlight-box">
                <p><strong>Pasos para Instalar Active Directory:</strong></p>
                <ol>
                    <li>Abre el <strong>Administrador del servidor</strong>.</li>
                    <li>Haz clic en <strong>Agregar Roles y características</strong>.</li>
                    <li>Selecciona <strong>Servicio Dominio de Active Directory</strong>.</li>
                    <li>Completa el asistente de instalación siguiendo las instrucciones.</li>
                </ol>
            </div>
<div class="image-reference">
    <img src="c:\Users\hp\Pictures\Screenshots\Screenshot 2025-07-29 174646.png" alt="Descargar e instalar Active Directory - Paso 1">
    <p>Primer paso para descargar e instalar Active Directory</p>
</div>

<div class="image-reference">
    <img src="c:\Users\hp\Pictures\Screenshots\Screenshot 2025-07-29 174724.png" alt="Descargar e instalar Active Directory - Paso 2">
    <p>Segundo paso para descargar e instalar Active Directory</p>
</div>
 <p>Una vez instalado, promueve el servidor a Controlador de Dominio:</p>
            <ul>
                <li>Ejecuta el comando <code>DCPRIMO</code> en la barra de inicio rápida.</li>
                <li>Ingresa el nombre del dominio (por ejemplo en mi caso le puse,  <code>server.com</code>).</li>
                <li>Configura la contraseña del administrador.</li>
                <li>Finaliza el proceso de promoción.</li>
            </ul>
            <section class="content-section" id="dominio">
    <h2>Configuración del Dominio</h2>
    <p>Una vez instalado Active Directory, debes verificar que el servidor esté correctamente conectado al dominio.</p>

    <div class="image-reference">
        <img src="c:\Users\hp\Pictures\Screenshots\Screenshot 2025-07-29 175921.png" alt="Configuración de Usuarios y Equipos de Active Directory">
        <p>Administración de Usuarios y Equipos de Active Directory</p>
    </div>

    <p>En esta imagen puedes ver la estructura de usuarios y equipos en Active Directory.</p>

    <div class="image-reference">
        <img src="c:\Users\hp\Pictures\Screenshots\Screenshot 2025-07-29 180235.png" alt="Configuración del Nombre del Equipo en el Dominio">
        <p>Verificación del nombre del equipo en el dominio</p>
    </div>

    <p>La segunda imagen muestra cómo verificar el nombre del equipo y su pertenencia al dominio.</p>
</section>
</section>
<section class="content-section" id="gpo">
    <h2>Creación y Gestión de Políticas de Grupo (GPO)</h2>
    <p>Las Políticas de Grupo (GPO) son herramientas que permiten aplicar configuraciones estándar a usuarios y equipos en un dominio. Las GPO se utilizan para definir reglas comunes, como restricciones de software, ajustes del sistema operativo y políticas de seguridad.</p>

    <div class="highlight-box">
        <p><strong>Pasos para Crear una Política de Grupo:</strong></p>
        <ol>
            <li>Abre <strong>Herramientas Administrativas</strong>.</li>
            <li>Selecciona <strong>Administración de Directivas de Grupo</strong>.</li>
            <li>En el panel izquierdo, haz clic derecho en <strong>Objetos de Directivas de grupo</strong> y selecciona <strong>Nuevo</strong>.</li>
            <li>Asigna un nombre a la nueva política (por ejemplo, <code>Política_Ejemplo</code>).</li>
        </ol>
    </div>

    <div class="image-reference">
        <img src="c:\Users\hp\Pictures\Screenshots\Screenshot 2025-07-29 200245.png" alt="Administración de Directivas de Grupo - Vínculos y Filtro de Seguridad">
        <p>Administración de Directivas de Grupo: Vínculos y Filtro de Seguridad</p>
    </div>

    <p>En esta imagen puedes ver cómo vincular el GPO a dominios, unidades organizativas y aplicar filtros de seguridad.</p>

    <div class="image-reference">
        <img src="c:\Users\hp\Pictures\Screenshots\Screenshot 2025-07-29 200357.png" alt="Grupos y Usuarios con Permisos Específicos para el GPO">
        <p>Grupos y Usuarios con Permisos Específicos para el GPO</p>
    </div>

    <p>La segunda imagen muestra los grupos y usuarios que tienen permisos específicos para editar, eliminar o leer las configuraciones del GPO.</p>

    <div class="image-reference">
        <img src="c:\Users\hp\Pictures\Screenshots\Screenshot 2025-07-29 200519.png" alt="Editor de Directivas de Grupo Local">
        <p>Editor de Directivas de Grupo Local</p>
    </div>

    <p>La tercera imagen muestra el Editor de Directivas de Grupo Local, donde puedes configurar políticas específicas para el equipo o el usuario.</p>

    <p>Edita la política y configura las directivas necesarias:</p>
    <ul>
        <li>Haz clic derecho sobre la política creada y selecciona <strong>Editar</strong>.</li>
        <li>Navega por las diferentes secciones para configurar las políticas deseadas.</li>
    </ul>

    <p>Aplica y vincula la GPO:</p>
    <ul>
        <li>Vincula la política al dominio o a un objeto específico (como un grupo de usuarios o equipos).</li>
        <li>Aplica la política utilizando <code>Gpupdate /force</code> en la línea de comandos.</li>
    </ul>
</section>
        </section>

    </div>

</body>
</html>
