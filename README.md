<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Romanel | Joias e Semi Joias Elegantes</title>
    <!-- Google Fonts & Font Awesome -->
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700;800&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: #000000;
            color: #000000;
            scroll-behavior: smooth;
        }

        h1, h2, h3, .logo-text {
            font-family: 'Playfair Display', serif;
        }

        /* Container padrão */
        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* HEADER */
        .header {
            background: #000000;
            box-shadow: 0 8px 20px rgba(0,0,0,0.02), 0 2px 6px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(2px);
        }
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 18px 0;
            flex-wrap: wrap;
            gap: 16px;
        }
        .logo-area {
            display: flex;
            align-items: center;
            gap: 12px;
            cursor: pointer;
        }
        .logo-icon {
            font-size: 2rem;
            color: #b1a962;
        }
        .logo-text {
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: 2px;
            color: #3e2a1f;
            border-right: 2px solid #e4cfb5;
            padding-right: 12px;
        }
        .logo-sub {
            font-size: 0.75rem;
            font-weight: 400;
            color: #ffffff;
            letter-spacing: 1px;
        }
        .nav-links {
            display: flex;
            gap: 32px;
            align-items: center;
            flex-wrap: wrap;
        }
        .nav-links a {
            text-decoration: none;
            font-weight: 500;
            color: #ffffff;
            transition: 0.3s;
            font-size: 1rem;
        }
        .nav-links a:hover {
            color: #ffffff;
        }
        .user-greeting {
            display: flex;
            align-items: center;
            gap: 12px;
            background: #f9ede2;
            padding: 6px 18px;
            border-radius: 40px;
        }
        .user-name {
            font-weight: 600;
            color: #ffffff;
        }
        .logout-btn {
            background: none;
            border: none;
            color: #c29a4f;
            font-weight: 500;
            cursor: pointer;
            font-size: 0.85rem;
            transition: 0.2s;
        }
        .logout-btn:hover {
            color: #c0392b;
        }
        .cadastro-link {
            background: #ffffff;
            color: white !important;
            padding: 8px 22px;
            border-radius: 40px;
            transition: 0.3s;
        }
        .cadastro-link:hover {
            background: #ffffff;
            transform: scale(1.02);
        }

        /* Hero */
        .hero {
            background: linear-gradient(105deg, #fff6ed 0%, #faeedf 100%);
            padding: 70px 0 60px;
            border-bottom: 1px solid #f0e0cf;
        }
        .hero-grid {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 40px;
        }
        .hero-text {
            flex: 1;
        }
        .hero-text h1 {
            font-size: 3.2rem;
            font-weight: 700;
            color: #3e2a1f;
            line-height: 1.2;
        }
        .hero-text p {
            font-size: 1.1rem;
            margin: 24px 0 32px;
            color: #000000;
        }
        .btn-gold {
            background: #dbb88c;
            border: none;
            padding: 14px 32px;
            border-radius: 48px;
            font-weight: 600;
            color: #2d241c;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.3s;
            display: inline-block;
            text-decoration: none;
        }
        .btn-gold:hover {
            background: #c9a172;
            transform: translateY(-3px);
            box-shadow: 0 12px 20px rgba(0,0,0,0.05);
        }
        .hero-image {
            flex: 1;
            text-align: center;
        }
        .hero-image img {
            max-width: 100%;
            border-radius: 32px;
            box-shadow: 0 20px 30px -12px rgba(0,0,0,0.1);
        }

        /* Products Section */
        .section-title {
            text-align: center;
            font-size: 2.3rem;
            font-weight: 600;
            margin: 60px 0 20px;
            color: #3e2a1f;
            position: relative;
        }
        .section-title:after {
            content: '';
            display: block;
            width: 70px;
            height: 3px;
            background: #fffdfa;
            margin: 12px auto 0;
            border-radius: 3px;
        }
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 32px;
            margin: 40px 0 60px;
        }
        .product-card {
            background: white;
            border-radius: 28px;
            overflow: hidden;
            box-shadow: 0 12px 28px rgba(0,0,0,0.04);
            transition: all 0.3s ease;
            text-align: center;
            cursor: default;
        }
        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 30px rgba(0,0,0,0.08);
        }
        .product-img {
            width: 100%;
            height: 280px;
            object-fit: cover;
            transition: transform 0.5s;
        }
        .product-card:hover .product-img {
            transform: scale(1.02);
        }
        .product-info {
            padding: 20px 16px 24px;
        }
        .product-title {
            font-size: 1.3rem;
            font-weight: 600;
            font-family: 'Playfair Display', serif;
            color: #4e3624;
        }
        .product-price {
            color: #b17e55;
            font-weight: 600;
            font-size: 1.2rem;
            margin: 10px 0;
        }
        .btn-product {
            background: #f3ede8;
            border: none;
            padding: 8px 18px;
            border-radius: 40px;
            font-weight: 500;
            color: #5c3f2b;
            margin-top: 8px;
            cursor: pointer;
            transition: 0.2s;
        }
        .btn-product:hover {
            background: #ffffff;
            color: white;
        }

        /* Registration Section */
        .register-section {
            background: linear-gradient(125deg, #fef7f0, #fff9f3);
            border-radius: 48px;
            margin: 40px 0 70px;
            padding: 48px 40px;
            box-shadow: 0 8px 24px rgba(0,0,0,0.02);
        }
        .register-container {
            display: flex;
            flex-wrap: wrap;
            gap: 48px;
            align-items: center;
        }
        .register-info {
            flex: 1;
        }
        .register-info h3 {
            font-size: 2rem;
            font-weight: 700;
            color: #3e2a1f;
        }
        .register-info p {
            margin-top: 16px;
            color: #7d6248;
        }
        .register-form {
            flex: 1;
            background: white;
            padding: 32px 28px;
            border-radius: 32px;
            box-shadow: 0 20px 35px -10px rgba(0,0,0,0.05);
        }
        .form-group {
            margin-bottom: 18px;
        }
        .form-group input {
            width: 100%;
            padding: 14px 18px;
            border: 1px solid #e9dbcf;
            border-radius: 48px;
            font-family: 'Poppins', sans-serif;
            font-size: 0.9rem;
            background: #fffcf9;
            transition: 0.2s;
        }
        .form-group input:focus {
            outline: none;
            border-color: hsl(0, 0%, 100%);
            box-shadow: 0 0 0 3px rgba(219,184,140,0.2);
        }
        .register-btn {
            width: 100%;
            background: #dbb88c;
            border: none;
            padding: 14px;
            border-radius: 48px;
            font-weight: bold;
            font-size: 1rem;
            color: #2d241c;
            cursor: pointer;
            transition: 0.3s;
        }
        .register-btn:hover {
            background: #c6a27a;
        }
        .form-message {
            margin-top: 16px;
            font-size: 0.85rem;
            text-align: center;
        }
        .success-msg {
            color: #2b7a4b;
        }
        .error-msg {
            color: #c0392b;
        }

        /* Footer */
        .footer {
            background: #2b241f;
            color: #e7cfba;
            padding: 48px 0 24px;
            margin-top: 40px;
        }
        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 30px;
        }
        .footer-col h4 {
            font-family: 'Playfair Display', serif;
            margin-bottom: 16px;
            color: #f1dbc4;
        }
        .footer-col p, .footer-col i {
            margin: 6px 0;
            color: #cdb79e;
        }
        .social-icons i {
            font-size: 1.6rem;
            margin-right: 18px;
            transition: 0.2s;
        }
        .social-icons i:hover {
            color: #dbb88c;
        }
        .copyright {
            text-align: center;
            margin-top: 48px;
            padding-top: 20px;
            border-top: 1px solid #4a3a2f;
            font-size: 0.8rem;
        }
        @media (max-width: 800px) {
            .nav-container { flex-direction: column; }
            .hero-text h1 { font-size: 2.4rem; }
            .register-section { padding: 32px 20px; }
        }


        .logo-text {
    font-family: 'Playfair Display', serif;
    font-size: 1.8rem;
    font-weight: 700;
    color: #dbb88c;
}
.logo-slogan {
    font-size: 0.7rem;
    color: #c0b472;
    margin-left: 8px;
}

    </style>
</head>

<body>



<header class="header">
    <div class="container nav-container">
        <div class="logo-area" onclick="scrollToTop()">
    <span class="logo-text">ROMANEL</span>
    <span class="logo-slogan">JOIAS & SEMI JOIAS</span>
</div>
        <div class="nav-links">
            <a href="#home">Início</a>
            <a href="#produtos">Coleções</a>
            <a href="#cadastro">Cadastro</a>
            <a href="#contato">Contato</a>
            <div id="userStatusArea">
                <!-- user dynamic content -->
            </div>
        </div>
    </div>
</header>

<main>
    <!-- Hero Section (Home) -->
    <section id="home" class="hero">
        <div class="container hero-grid">
            <div class="hero-text">
                <h1>Elegância que <br>dura gerações</h1>
                <p>Descubra o brilho exclusivo das nossas joias e semi joias. Peças únicas para momentos inesquecíveis.</p>
                <a href="#produtos" class="btn-gold">Explorar Coleção <i class="fas fa-arrow-right"></i></a>
            </div>
            <div class="hero-image">
                <img src="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=600&h=450&fit=crop" alt="Joia Romanel">
            </div>
        </div>
    </section>

    <!-- Products -->
    <div class="container" id="produtos">
        <h2 class="section-title">Joias & Semi Joias Exclusivas</h2>
        <div class="products-grid">
            <div class="product-card">
                <img class="product-img" src="https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?w=400&h=300&fit=crop" alt="Colar Ouro Rosé">
                <div class="product-info">
                    <h3 class="product-title">Colar Solário</h3>
                    <div class="product-price">R$ 890,00</div>
                    <button class="btn-product" onclick="alert('✨ Peça adicionada ao carrinho (demonstração)')"><i class="fas fa-shopping-bag"></i> Interessado</button>
                </div>
            </div>
            <div class="product-card">
                <img class="product-img" src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=400&h=300&fit=crop" alt="Brincos Diamante">
                <div class="product-info">
                    <h3 class="product-title">Brincos Luna</h3>
                    <div class="product-price">R$ 1.290,00</div>
                    <button class="btn-product" onclick="alert('✨ Peça adicionada ao carrinho (demonstração)')"><i class="fas fa-shopping-bag"></i> Interessado</button>
                </div>
            </div>
            <div class="product-card">
                <img class="product-img" src="https://images.unsplash.com/photo-1611652022419-a9419f74343d?w=400&h=300&fit=crop" alt="Pulseira Classic">
                <div class="product-info">
                    <h3 class="product-title">Pulseira Veneza</h3>
                    <div class="product-price">R$ 540,00</div>
                    <button class="btn-product" onclick="alert('✨ Peça adicionada ao carrinho (demonstração)')"><i class="fas fa-shopping-bag"></i> Interessado</button>
                </div>
            </div>
            <div class="product-card">
                <img class="product-img" src="https://images.unsplash.com/photo-1589128777073-263566ae5e4d?w=400&h=300&fit=crop" alt="Anel Safira">
                <div class="product-info">
                    <h3 class="product-title">Anel Celeste</h3>
                    <div class="product-price">R$ 2.150,00</div>
                    <button class="btn-product" onclick="alert('✨ Peça adicionada ao carrinho (demonstração)')"><i class="fas fa-shopping-bag"></i> Interessado</button>
                </div>
            </div>
            <div class="product-card">
                <img class="product-img" src="https://images.unsplash.com/photo-1603561827638-8b6a8a7f8ff1?w=400&h=300&fit=crop" alt="Conjunto Pérola">
                <div class="product-info">
                    <h3 class="product-title">Conjunto Margarida</h3>
                    <div class="product-price">R$ 1.890,00</div>
                    <button class="btn-product" onclick="alert('✨ Peça adicionada ao carrinho (demonstração)')"><i class="fas fa-shopping-bag"></i> Interessado</button>
                </div>
            </div>
            <div class="product-card">
                <img class="product-img" src="https://images.unsplash.com/photo-1617038260897-41a1f14a8ca0?w=400&h=300&fit=crop" alt="Tornozeleira">
                <div class="product-info">
                    <h3 class="product-title">Tornozeleira Aurora</h3>
                    <div class="product-price">R$ 430,00</div>
                    <button class="btn-product" onclick="alert('✨ Peça adicionada ao carrinho (demonstração)')"><i class="fas fa-shopping-bag"></i> Interessado</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Registration Section (cadastro) -->
    <div class="container" id="cadastro">
        <div class="register-section">
            <div class="register-container">
                <div class="register-info">
                    <h3><i class="fas fa-star-of-life"></i> Clube Romanel</h3>
                    <p>Cadastre-se agora e receba ofertas exclusivas, lançamentos em primeira mão e 10% de desconto na primeira compra.</p>
                    <p><i class="fas fa-gem"></i> Benefícios:<br>✔️ Frete grátis para membros<br>✔️ Brindes especiais<br>✔️ Atendimento VIP</p>
                </div>
                <div class="register-form">
                    <h3 style="font-family: 'Playfair Display'; margin-bottom: 20px; color:#3e2a1f;">Criar Conta</h3>
                    <form id="registerForm">
                        <div class="form-group">
                            <input type="text" id="regName" placeholder="Nome completo" required>
                        </div>
                        <div class="form-group">
                            <input type="email" id="regEmail" placeholder="Seu melhor e-mail" required>
                        </div>
                        <div class="form-group">
                            <input type="password" id="regPassword" placeholder="Senha (mínimo 6 caracteres)" required>
                        </div>
                        <div class="form-group">
                            <input type="password" id="regConfirm" placeholder="Confirmar senha" required>
                        </div>
                        <button type="submit" class="register-btn"><i class="fas fa-user-plus"></i> Cadastrar</button>
                        <div id="formFeedback" class="form-message"></div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</main>

<footer id="contato" class="footer">
    <div class="container footer-content">
        <div class="footer-col">
            <h4>ROMANEL</h4>
            <p>Joias e semi joias com design atemporal.</p>
            <p><i class="fas fa-map-marker-alt"></i> Av. das Joias, 1250 - São Paulo</p>
            <p><i class="fas fa-phone-alt"></i> +55 (11) 3456-7890</p>
        </div>
        <div class="footer-col">
            <h4>Atendimento</h4>
            <p>Seg - Sex: 9h às 19h</p>
            <p>E-mail: contato@romanel.com.br</p>
        </div>
        <div class="footer-col social-icons">
            <h4>Siga-nos</h4>
            <i class="fab fa-instagram"></i>
            <i class="fab fa-facebook"></i>
            <i class="fab fa-pinterest"></i>
            <i class="fab fa-youtube"></i>
        </div>
    </div>
    <div class="container copyright">
        <p>&copy; 2025 Romanel Joias. Todos os direitos reservados. | Brilho que encanta.</p>
    </div>
</footer>

<script>
    // ----------------------------- Gerenciamento de Cadastro, Login e UI -----------------------------
    // Chaves do localStorage
    const STORAGE_USERS = "romanel_users";
    const STORAGE_CURRENT_USER = "romanel_current_user";

    // Carregar dados iniciais
    let users = [];
    let currentUser = null;

    // Funções auxiliares
    function loadData() {
        const storedUsers = localStorage.getItem(STORAGE_USERS);
        if(storedUsers) {
            users = JSON.parse(storedUsers);
        } else {
            // Dados iniciais vazios, sem usuários pré-cadastrados (apenas demonstração)
            users = [];
        }
        const storedCurrent = localStorage.getItem(STORAGE_CURRENT_USER);
        if(storedCurrent && storedCurrent !== "null") {
            try {
                currentUser = JSON.parse(storedCurrent);
            } catch(e) { currentUser = null; }
        } else {
            currentUser = null;
        }
    }

    function saveUsers() {
        localStorage.setItem(STORAGE_USERS, JSON.stringify(users));
    }

    function saveCurrentUser() {
        if(currentUser) {
            localStorage.setItem(STORAGE_CURRENT_USER, JSON.stringify(currentUser));
        } else {
            localStorage.removeItem(STORAGE_CURRENT_USER);
        }
    }

    // Atualizar a interface do header (saudação / logout / botão cadastro)
    function updateUserInterface() {
        const userStatusArea = document.getElementById("userStatusArea");
        if(!userStatusArea) return;

        if(currentUser && currentUser.name) {
            // Usuário logado: mostrar saudação e botão sair
            userStatusArea.innerHTML = `
                <div class="user-greeting">
                    <span class="user-name"><i class="fas fa-user-circle"></i> Olá, ${currentUser.name.split(' ')[0]}</span>
                    <button class="logout-btn" id="logoutButton"><i class="fas fa-sign-out-alt"></i> Sair</button>
                </div>
            `;
            const logoutBtn = document.getElementById("logoutButton");
            if(logoutBtn) {
                logoutBtn.addEventListener("click", (e) => {
                    e.preventDefault();
                    logoutUser();
                });
            }
        } else {
            // Nenhum usuário: mostrar botão Cadastre-se que rola até o formulário
            userStatusArea.innerHTML = `<a href="#cadastro" class="cadastro-link"><i class="fas fa-user-plus"></i> Cadastre-se</a>`;
        }
    }

    // Logout
    function logoutUser() {
        currentUser = null;
        saveCurrentUser();
        updateUserInterface();
        // Mostrar mensagem no formulário caso esteja visível
        const feedDiv = document.getElementById("formFeedback");
        if(feedDiv) {
            feedDiv.innerHTML = '<span class="success-msg">🔓 Você saiu da sua conta. Cadastre-se ou faça login.</span>';
            setTimeout(() => { if(feedDiv) feedDiv.innerHTML = ''; }, 3000);
        }
        // Limpar qualquer erro no formulário
        const form = document.getElementById("registerForm");
        if(form) form.reset();
    }

    // Registrar novo usuário
    function registerUser(name, email, password) {
        // Validações
        if(!name || name.trim().length < 3) {
            return { success: false, message: "Nome deve ter pelo menos 3 caracteres." };
        }
        const emailRegex = /^[^\s@]+@([^\s@]+\.)+[^\s@]+$/;
        if(!emailRegex.test(email)) {
            return { success: false, message: "E-mail inválido." };
        }
        if(password.length < 6) {
            return { success: false, message: "A senha precisa ter no mínimo 6 caracteres." };
        }
        // Verifica se email já cadastrado
        const emailExists = users.some(user => user.email === email);
        if(emailExists) {
            return { success: false, message: "Este e-mail já está cadastrado. Use outro ou faça login." };
        }
        // Criar novo user
        const newUser = {
            id: Date.now(),
            name: name.trim(),
            email: email,
            password: password  // Em ambiente real hash, apenas demo
        };
        users.push(newUser);
        saveUsers();
        // Auto login após cadastro
        currentUser = { id: newUser.id, name: newUser.name, email: newUser.email };
        saveCurrentUser();
        updateUserInterface();
        return { success: true, message: "✅ Cadastro realizado com sucesso! Bem-vindo(a) à Romanel." };
    }

    // Evento do formulário de cadastro
    function setupFormHandler() {
        const form = document.getElementById("registerForm");
        if(!form) return;
        form.addEventListener("submit", function(e) {
            e.preventDefault();
            const name = document.getElementById("regName").value.trim();
            const email = document.getElementById("regEmail").value.trim();
            const password = document.getElementById("regPassword").value;
            const confirm = document.getElementById("regConfirm").value;
            const feedbackDiv = document.getElementById("formFeedback");
            
            if(password !== confirm) {
                feedbackDiv.innerHTML = '<span class="error-msg">❌ As senhas não conferem.</span>';
                setTimeout(() => { if(feedbackDiv) feedbackDiv.innerHTML = ''; }, 3000);
                return;
            }
            const result = registerUser(name, email, password);
            if(result.success) {
                feedbackDiv.innerHTML = `<span class="success-msg">${result.message}</span>`;
                form.reset();
                // Rolar levemente para header para mostrar saudação
                setTimeout(() => {
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                }, 200);
            } else {
                feedbackDiv.innerHTML = `<span class="error-msg">⚠️ ${result.message}</span>`;
            }
            setTimeout(() => {
                if(feedbackDiv && !feedbackDiv.innerHTML.includes("✅")) 
                    feedbackDiv.innerHTML = '';
                else if(feedbackDiv && feedbackDiv.innerHTML.includes("✅")) {
                    setTimeout(() => { if(feedbackDiv) feedbackDiv.innerHTML = ''; }, 4000);
                }
            }, 3500);
        });
    }

    // Scroll suave e highlight para cadastro
    function smoothScrollBehavior() {
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const hash = this.getAttribute('href');
                if(hash === "#" || hash === "") return;
                if(hash.startsWith("#")) {
                    const target = document.querySelector(hash);
                    if(target) {
                        e.preventDefault();
                        target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                    }
                }
            });
        });
    }

    // Botão de voltar ao topo com logo
    function scrollToTop() {
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }
    window.scrollToTop = scrollToTop;
    
    // Adicional: Pré carregar e sincronizar
    function init() {
        loadData();
        updateUserInterface();
        setupFormHandler();
        smoothScrollBehavior();
        // Injetar estilização extra se necessário
        // Caso o formulário receba focus e user já logado, manda informação amigável
        const regEmailInput = document.getElementById("regEmail");
        if(regEmailInput && currentUser) {
            regEmailInput.addEventListener("focus", () => {
                const msgDiv = document.getElementById("formFeedback");
                if(msgDiv && !msgDiv.innerText.includes("logado")) {
                    msgDiv.innerHTML = '<span class="success-msg">✨ Você está logado. Pode registrar outra conta também.</span>';
                    setTimeout(() => { if(msgDiv && msgDiv.innerHTML.includes("logado")) msgDiv.innerHTML = ''; }, 2500);
                }
            });
        }
        // Adicionar nota de boas vindas se usuário já logado no carregamento
        if(currentUser) {
            console.log(`Bem-vindo de volta, ${currentUser.name}`);
        }
    }

    init();
</script>
</body>
</html>
