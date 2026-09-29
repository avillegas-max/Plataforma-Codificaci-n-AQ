<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Sistema de Codificación Documental</title>

    <style>

        * {
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            margin: 0;
            background: #f4f7fa;
            color: #183247;
        }

        /* LOGIN */

        .login-container {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;

            background: linear-gradient(
                135deg,
                #e8f3fa,
                #ffffff
            );
        }

        .login-box {
            width: 400px;
            background: white;
            padding: 40px;

            border-radius: 15px;

            box-shadow:
                0 15px 45px rgba(0,0,0,0.12);
        }

        .logo {
            text-align: center;
            font-size: 30px;
            font-weight: bold;
            color: #111;
            letter-spacing: 2px;
        }

        .logo span {
            display: block;
            color: #168acb;
            font-size: 14px;
            letter-spacing: 4px;
        }

        .login-title {
            text-align: center;
            color: #064b83;
            margin-top: 25px;
        }

        .login-subtitle {
            text-align: center;
            color: #687887;
            font-size: 13px;
            margin-bottom: 30px;
        }

        .input-group {
            margin-bottom: 18px;
        }

        .input-group label {
            display: block;
            font-size: 13px;
            font-weight: bold;
            margin-bottom: 7px;
        }

        .input-group input {
            width: 100%;
            padding: 12px;

            border: 1px solid #ccd8e2;
            border-radius: 7px;

            outline: none;
        }

        .input-group input:focus {
            border-color: #0b6db7;
        }

        .btn-login {
            width: 100%;

            border: none;
            border-radius: 7px;

            padding: 13px;

            background: #0b6db7;
            color: white;

            font-weight: bold;

            cursor: pointer;
        }

        .btn-login:hover {
            background: #064b83;
        }

        .forgot {
            text-align: center;
            margin-top: 18px;
            color: #0b6db7;
            font-size: 13px;
            cursor: pointer;
        }

        /* APP */

        .app {
            display: none;
            min-height: 100vh;
        }

        .sidebar {
            width: 250px;

            position: fixed;
            left: 0;
            top: 0;
            bottom: 0;

            background: #063b67;

            padding: 25px 15px;

            color: white;
        }

        .sidebar-logo {
            text-align: center;
            font-weight: bold;
            font-size: 23px;
            margin-bottom: 40px;
        }

        .sidebar-logo span {
            display: block;
            font-size: 12px;
            color: #62c5ff;
        }

        .menu-button {
            width: 100%;

            border: none;
            background: transparent;

            color: white;

            text-align: left;

            padding: 13px;

            border-radius: 7px;

            cursor: pointer;

            margin-bottom: 7px;
        }

        .menu-button:hover,
        .menu-button.active {
            background: #0b78bd;
        }

        .logout {
            position: absolute;
            bottom: 25px;
            left: 15px;
            right: 15px;

            background: rgba(255,255,255,0.08);
        }

        .main {
            margin-left: 250px;
            padding: 30px;
        }

        .topbar {
            background: white;

            padding: 18px 25px;

            border-radius: 10px;

            display: flex;
            justify-content: space-between;
            align-items: center;

            margin-bottom: 25px;
        }

        .topbar h2 {
            margin: 0;
            color: #064b83;
        }

        .user {
            color: #687887;
            font-size: 13px;
        }

        /* DASHBOARD */

        .welcome {
            background: linear-gradient(
                110deg,
                #dceefa,
                #ffffff
            );

            padding: 30px;

            border-radius: 12px;

            border: 1px solid #d4e1ea;

            margin-bottom: 20px;
        }

        .welcome h1 {
            color: #064b83;
            margin-top: 0;
        }

        .cards {
            display: grid;

            grid-template-columns:
                repeat(3, 1fr);

            gap: 18px;
        }

        .card {
            background: white;

            padding: 25px;

            border-radius: 12px;

            border: 1px solid #d9e2ea;

            cursor: pointer;
        }

        .card:hover {
            box-shadow: 0 8px 25px rgba(0,0,0,0.08);
        }

        .card h3 {
            color: #064b83;
        }

        .card p {
            color: #687887;
            font-size: 13px;
        }

        /* FORM */

        .section {
            background: white;

            border-radius: 12px;

            padding: 25px;

            border: 1px solid #d9e2ea;
        }

        .section h2 {
            color: #064b83;
            margin-top: 0;
        }

        .form-grid {
            display: grid;

            grid-template-columns:
                repeat(2, 1fr);

            gap: 18px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group label {
            font-size: 13px;
            font-weight: bold;

            margin-bottom: 7px;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {

            padding: 11px;

            border: 1px solid #ccd8e2;

            border-radius: 7px;

            outline: none;
        }

        .full {
            grid-column: 1 / -1;
        }

        .code-box {
            margin-top: 25px;

            padding: 20px;

            background: #eef7fc;

            border: 1px dashed #72acd0;

            border-radius: 10px;

            text-align: center;
        }

        .code-title {
            color: #687887;
            font-size: 13px;
        }

        .generated-code {

            margin-top: 10px;

            font-size: 28px;

            font-weight: bold;

            color: #064b83;
        }

        .buttons {
            display: flex;

            justify-content: flex-end;

            gap: 10px;

            margin-top: 20px;
        }

        .btn {
            padding: 12px 20px;

            border: none;

            border-radius: 7px;

            cursor: pointer;

            font-weight: bold;
        }

        .btn-primary {
            background: #0b6db7;
            color: white;
        }

        .btn-success {
            background: #16865b;
            color: white;
        }

        /* TABLE */

        .table-container {
            overflow-x: auto;
        }

        table {
            width: 100%;

            border-collapse: collapse;

            font-size: 12px;
        }

        th {
            background: #d9eaf6;

            color: #173c57;

            padding: 11px;

            text-align: left;
        }

        td {
            padding: 10px;

            border-bottom:
                1px solid #e5ebef;
        }

        .status {
            background: #e8f7f0;

            color: #16865b;

            padding: 5px 9px;

            border-radius: 15px;

            font-size: 11px;

            font-weight: bold;
        }

        @media(max-width:900px) {

            .sidebar {
                width: 200px;
            }

            .main {
                margin-left: 200px;
            }

            .cards {
                grid-template-columns: 1fr;
            }

            .form-grid {
                grid-template-columns: 1fr;
            }

        }

    </style>
</head>


<body>


<!-- ========================= -->
<!-- LOGIN -->
<!-- ========================= -->

<div id="loginContainer" class="login-container">

    <div class="login-box">

        <div class="logo">
            AQUA
            <span>SERVICES</span>
        </div>

        <h2 class="login-title">
            Sistema de Codificación Documental
        </h2>

        <p class="login-subtitle">
            Sistema de Aseguramiento y Control de Calidad
        </p>


        <div class="input-group">

            <label>
                Correo electrónico
            </label>

            <input
                type="email"
                id="email"
                placeholder="correo@empresa.cl"
            >

        </div>


        <div class="input-group">

            <label>
                Contraseña
            </label>

            <input
                type="password"
                id="password"
                placeholder="••••••••"
            >

        </div>


        <button
            class="btn-login"
            onclick="login()"
        >
            INGRESAR
        </button>


        <div
            class="forgot"
            onclick="recuperarPassword()"
        >
            ¿Olvidaste tu contraseña?
        </div>

    </div>

</div>



<!-- ========================= -->
<!-- APLICACIÓN -->
<!-- ========================= -->

<div id="app" class="app">


    <!-- SIDEBAR -->

    <aside class="sidebar">

        <div class="sidebar-logo">

            AQUA

            <span>
                SERVICES
            </span>

        </div>


        <button
            class="menu-button active"
            onclick="mostrar('inicio', this)"
        >
            🏠 Inicio
        </button>


        <button
            class="menu-button"
            onclick="mostrar('nuevo', this)"
        >
            ➕ Nuevo documento
        </button>


        <button
            class="menu-button"
            onclick="mostrar('listado', this)"
        >
            📋 Listado Maestro
        </button>


        <button
            class="menu-button"
            onclick="mostrar('matriz', this)"
        >
            📊 Matriz de Trazabilidad
        </button>


        <button
            class="menu-button"
            onclick="mostrar('configuracion', this)"
        >
            ⚙ Configuración
        </button>


        <button
            class="menu-button logout"
            onclick="logout()"
        >
            🚪 Cerrar sesión
        </button>

    </aside>



    <!-- CONTENIDO -->

    <main class="main">


        <div class="topbar">

            <h2 id="tituloPagina">
                Inicio
            </h2>

            <span
                class="user"
                id="usuarioActual"
            ></span>

        </div>



        <!-- ========================= -->
        <!-- INICIO -->
        <!-- ========================= -->

        <section
            id="inicio"
            class="pagina"
        >

            <div class="welcome">

                <h1>
                    Sistema de Codificación Documental
                </h1>

                <p>
                    Generación y control automático de códigos documentales.
                </p>

            </div>


            <div class="cards">


                <div
                    class="card"
                    onclick="mostrarPorNombre('nuevo')"
                >

                    <h3>
                        📄 Nuevo documento
                    </h3>

                    <p>
                        Generar automáticamente el siguiente correlativo.
                    </p>

                </div>


                <div
                    class="card"
                    onclick="mostrarPorNombre('listado')"
                >

                    <h3>
                        📋 Listado Maestro
                    </h3>

                    <p>
                        Consultar los documentos registrados.
                    </p>

                </div>


                <div
                    class="card"
                    onclick="mostrarPorNombre('matriz')"
                >

                    <h3>
                        📊 Matriz de Trazabilidad
                    </h3>

                    <p>
                        Consultar la trazabilidad documental.
                    </p>

                </div>


            </div>

        </section>



        <!-- ========================= -->
        <!-- NUEVO DOCUMENTO -->
        <!-- ========================= -->

        <section
            id="nuevo"
            class="pagina"
            style="display:none"
        >

            <div class="section">

                <h2>
                    Nuevo documento
                </h2>


                <div class="form-grid">


                    <div class="form-group">

                        <label>
                            Tipo de proyecto
                        </label>

                        <select id="tipoProyecto">

                            <option value="interno">
                                Documento interno / proyecto pequeño
                            </option>

                            <option value="grande">
                                Proyecto grande
                            </option>

                        </select>

                    </div>



                    <div class="form-group">

                        <label>
                            Cliente
                        </label>

                        <select id="cliente">

                            <option value="">
                                Seleccionar cliente
                            </option>

                            <option value="AN">
                                Alto Norte
                            </option>

                            <option value="DPM">
                                Despromin
                            </option>

                        </select>

                    </div>



                    <div class="form-group">

                        <label>
                            Número proyecto cliente
                        </label>

                        <input
                            id="numeroProyecto"
                            placeholder="Ej: 01"
                        >

                    </div>



                    <div class="form-group">

                        <label>
                            Área / Sistema
                        </label>

                        <select id="area">

                            <option value="AD">
                                Alta Dirección
                            </option>

                            <option value="QA">
                                Gestión Calidad
                            </option>

                            <option value="QC">
                                Control Calidad
                            </option>

                            <option value="PR">
                                Producción y Operaciones
                            </option>

                            <option value="ING">
                                Ingeniería y Proyectos
                            </option>

                            <option value="SEC">
                                Secretaría
                            </option>

                            <option value="ADQ">
                                Adquisiciones
                            </option>

                            <option value="VEN">
                                Ventas y Cotizaciones
                            </option>

                            <option value="RRHH">
                                Recursos Humanos
                            </option>

                            <option value="SSO">
                                Salud y Seguridad Ocupacional
                            </option>

                            <option value="MA">
                                Medio Ambiente
                            </option>

                            <option value="MANT">
                                Mantenimiento Equipos
                            </option>

                            <option value="SIG">
                                Gestión Integrada
                            </option>

                        </select>

                    </div>



                    <div class="form-group">

                        <label>
                            Tipo de documento
                        </label>

                        <select id="tipoDocumento">

                            <option value="PROC">
                                Procedimiento
                            </option>

                            <option value="INS">
                                Instructivo
                            </option>

                            <option value="REG">
                                Registro
                            </option>

                            <option value="MAN">
                                Manual
                            </option>

                            <option value="PL">
                                Plan
                            </option>

                            <option value="PROG">
                                Programa
                            </option>

                            <option value="ESQ">
                                Esquema
                            </option>

                            <option value="MAT">
                                Matriz
                            </option>

                            <option value="PLN">
                                Plano
                            </option>

                            <option value="INF">
                                Informe
                            </option>

                            <option value="PAC">
                                Plan de Aseguramiento Calidad
                            </option>

                            <option value="PROT">
                                Protocolo
                            </option>

                            <option value="PIE">
                                Plan de Inspección Ensayo
                            </option>

                            <option value="CHK">
                                Check List
                            </option>

                            <option value="ORG">
                                Organigrama
                            </option>

                        </select>

                    </div>



                    <div class="form-group">

                        <label>
                            Revisión
                        </label>

                        <select id="revision">

                            <option value="Rev0">
                                Rev0
                            </option>

                            <option value="Rev01">
                                Rev01
                            </option>

                            <option value="Rev02">
                                Rev02
                            </option>

                        </select>

                    </div>



                    <div class="form-group full">

                        <label>
                            Nombre del documento
                        </label>

                        <input
                            id="nombreDocumento"
                            placeholder="Ej: Procedimiento de Control Documental"
                        >

                    </div>


                </div>



                <!-- CÓDIGO -->

                <div class="code-box">

                    <div class="code-title">
                        CÓDIGO PROPUESTO
                    </div>

                    <div
                        id="codigoGenerado"
                        class="generated-code"
                    >
                        —
                    </div>

                </div>



                <div class="buttons">

                    <button
                        class="btn btn-primary"
                        onclick="generarCodigo()"
                    >
                        GENERAR CÓDIGO
                    </button>


                    <button
                        class="btn btn-success"
                        onclick="guardarDocumento()"
                    >
                        GUARDAR
                    </button>

                </div>

            </div>

        </section>



        <!-- ========================= -->
        <!-- LISTADO -->
        <!-- ========================= -->

        <section
            id="listado"
            class="pagina"
            style="display:none"
        >

            <div class="section">

                <h2>
                    Listado Maestro
                </h2>

                <div class="table-container">

                    <table>

                        <thead>

                            <tr>

                                <th>
                                    N°
                                </th>

                                <th>
                                    Código
                                </th>

                                <th>
                                    Documento
                                </th>

                                <th>
                                    Proyecto
                                </th>

                                <th>
                                    Tipo
                                </th>

                                <th>
                                    Área
                                </th>

                                <th>
                                    Revisión
                                </th>

                                <th>
                                    Estado
                                </th>

                            </tr>

                        </thead>


                        <tbody id="tablaListado">

                        </tbody>

                    </table>

                </div>

            </div>

        </section>



        <!-- ========================= -->
        <!-- MATRIZ -->
        <!-- ========================= -->

        <section
            id="matriz"
            class="pagina"
            style="display:none"
        >

            <div class="section">

                <h2>
                    Matriz de Trazabilidad
                </h2>


                <div class="table-container">

                    <table>

                        <thead>

                            <tr>

                                <th>
                                    N°
                                </th>

                                <th>
                                    Código
                                </th>

                                <th>
                                    Documento
                                </th>

                                <th>
                                    Proyecto
                                </th>

                                <th>
                                    Área
                                </th>

                                <th>
                                    Tipo
                                </th>

                                <th>
                                    Revisión
                                </th>

                            </tr>

                        </thead>


                        <tbody id="tablaMatriz">

                        </tbody>

                    </table>

                </div>

            </div>

        </section>



        <!-- ========================= -->
        <!-- CONFIGURACIÓN -->
        <!-- ========================= -->

        <section
            id="configuracion"
            class="pagina"
            style="display:none"
        >

            <div class="section">

                <h2>
                    Configuración
                </h2>

                <p>
                    Sistema conectado a Firebase.
                </p>

                <p>
                    Los usuarios y permisos serán administrados mediante Firebase Authentication.
                </p>

                <p>
                    Los documentos serán sincronizados con los archivos corporativos.
                </p>

            </div>

        </section>


    </main>

</div>



<!-- ========================= -->
<!-- FIREBASE -->
<!-- ========================= -->

<script type="module">

    import {
        initializeApp
    }

    from
    "https://www.gstatic.com/firebasejs/12.2.1/firebase-app.js";


    import {

        getAuth,

        signInWithEmailAndPassword,

        sendPasswordResetEmail,

        signOut,

        onAuthStateChanged

    }

    from
    "https://www.gstatic.com/firebasejs/12.2.1/firebase-auth.js";


    /*
    ==========================================================
    PEGA AQUÍ TU CONFIGURACIÓN DE FIREBASE
    ==========================================================
    */

    const firebaseConfig = {

        apiKey: "TU_API_KEY",

        authDomain:
            "TU-PROYECTO.firebaseapp.com",

        projectId:
            "TU-PROYECTO",

        storageBucket:
            "TU-PROYECTO.firebasestorage.app",

        messagingSenderId:
            "TU_SENDER_ID",

        appId:
            "TU_APP_ID"

    };


    const app =
        initializeApp(firebaseConfig);


    const auth =
        getAuth(app);



    /* LOGIN */

    window.login = async function(){

        const email =
            document.getElementById("email").value;

        const password =
            document.getElementById("password").value;


        try{

            await signInWithEmailAndPassword(
                auth,
                email,
                password
            );

        }

        catch(error){

            alert(
                "Correo o contraseña incorrectos."
            );

            console.error(error);

        }

    };



    /* RECUPERACIÓN */

    window.recuperarPassword =
    async function(){

        const email =
            document.getElementById("email").value;


        if(!email){

            alert(
                "Ingresa tu correo electrónico."
            );

            return;

        }


        try{

            await sendPasswordResetEmail(
                auth,
                email
            );


            alert(
                "Se envió el correo de recuperación."
            );

        }

        catch(error){

            alert(
                "No fue posible enviar el correo."
            );

        }

    };



    /* SESIÓN */

    window.logout =
    async function(){

        await signOut(auth);

    };



    /* ESTADO */

    onAuthStateChanged(
        auth,
        user => {

            const login =
                document.getElementById(
                    "loginContainer"
                );

            const app =
                document.getElementById(
                    "app"
                );


            if(user){

                login.style.display =
                    "none";

                app.style.display =
                    "flex";


                document.getElementById(
                    "usuarioActual"
                ).innerText =
                    user.email;

            }

            else{

                login.style.display =
                    "flex";

                app.style.display =
                    "none";

            }

        }

    );



    /*
    ==========================================================
    NAVEGACIÓN
    ==========================================================
    */

    window.mostrar =
    function(id, boton){

        document
        .querySelectorAll(".pagina")
        .forEach(
            p =>
            p.style.display = "none"
        );


        document.getElementById(id)
        .style.display = "block";


        document
        .querySelectorAll(".menu-button")
        .forEach(
            b =>
            b.classList.remove("active")
        );


        if(boton){

            boton.classList.add("active");

        }


        const titulos = {

            inicio:
                "Inicio",

            nuevo:
                "Nuevo documento",

            listado:
                "Listado Maestro",

            matriz:
                "Matriz de Trazabilidad",

            configuracion:
                "Configuración"

        };


        document.getElementById(
            "tituloPagina"
        ).innerText =
            titulos[id];

    };



    window.mostrarPorNombre =
    function(id){

        mostrar(id);

    };



    /*
    ==========================================================
    GENERACIÓN DEL CÓDIGO
    ==========================================================
    */

    window.generarCodigo =
    function(){

        const tipoProyecto =
            document.getElementById(
                "tipoProyecto"
            ).value;


        const cliente =
            document.getElementById(
                "cliente"
            ).value;


        const numeroProyecto =
            document.getElementById(
                "numeroProyecto"
            ).value;


        const area =
            document.getElementById(
                "area"
            ).value;


        const tipo =
            document.getElementById(
                "tipoDocumento"
            ).value;


        const revision =
            document.getElementById(
                "revision"
            ).value;



        /*
        IMPORTANTE:

        Por ahora colocamos 01 como
        demostración.

        En la siguiente etapa el número
        será consultado automáticamente
        desde tus datos históricos.
        */


        const correlativo =
            "01";


        let codigo;


        if(
            tipoProyecto === "grande"
        ){

            if(
                !cliente ||
                !numeroProyecto
            ){

                alert(
                    "Para un proyecto grande debes ingresar cliente y número de proyecto."
                );

                return;

            }


            codigo =
                `AQ-${cliente}-${numeroProyecto}-${area}-${tipo}-${correlativo}-${revision}`;

        }

        else{

            codigo =
                `AQ-${area}-${tipo}-${correlativo}-${revision}`;

        }


        document.getElementById(
            "codigoGenerado"
        ).innerText =
            codigo;

    };



    /*
    ==========================================================
    GUARDAR
    ==========================================================
    */

    window.guardarDocumento =
    function(){

        const codigo =
            document.getElementById(
                "codigoGenerado"
            ).innerText;


        const nombre =
            document.getElementById(
                "nombreDocumento"
            ).value;


        if(codigo === "—"){

            alert(
                "Primero debes generar el código."
            );

            return;

        }


        if(!nombre){

            alert(
                "Ingresa el nombre del documento."
            );

            return;

        }


        alert(
            "Documento preparado para registrar:\n\n"
            +
            codigo
            +
            "\n\n"
            +
            nombre
        );

    };

</script>


</body>
</html>
