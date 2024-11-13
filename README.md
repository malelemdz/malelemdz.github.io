<html><head><base href="." />
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#02132A">
<title>Clon de Malele - Beacons</title>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  background: #02132A; /* Solid color background */
  color: #FFFFFF;
  line-height: 1.6;
  min-height: 100vh; /* Ensure full viewport height */
}

.container {
  max-width: 680px;
  margin: 0 auto;
  padding: 20px;
  background: radial-gradient(circle at center top, #071B3C 0%, #02132A 100%);
  min-height: 100vh; /* Make container full height */
}

.profile-header {
  text-align: center;
  margin-bottom: 30px;
  position: relative;
}

.cover-image {
  width: 100%;
  height: 220px;  /* Increased from 180px to 220px */
  object-fit: cover;
  border-radius: 12px;
  margin-bottom: -70px;  /* Adjusted from -60px to -70px to let cover image overlap more with profile pic */
}

.profile-image {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  margin-bottom: 15px;
  object-fit: cover;
  position: relative;
  border: 4px solid #FFFFFF;
}

.profile-name {
  color: #FFFFFF;
  margin-bottom: 10px;
}

.profile-bio {
  color: #FFFFFF;
  opacity: 0.9;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-bottom: 30px;
}

.social-icon {
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.2s;
}

.social-icon:hover {
  transform: scale(1.1);
}

.social-icon svg {
  fill: #FFFFFF;
  width: 22px;
  height: 22px;
  transition: fill 0.2s;
}

.social-icon:hover svg {
  fill: #03CDBA;
}

.link-button {
  display: block;
  background: #FFFFFF;
  padding: 16px;
  margin-bottom: 16px;
  border-radius: 8px;
  text-decoration: none;
  color: #02132A;
  font-weight: 500;
  box-shadow: 0 2px 5px rgba(0,0,0,0.2);
  transition: all 0.2s ease;
}

.link-button:hover {
  transform: translateY(-2px);
  background: #03CDBA;
  color: #FFFFFF;
}

.error-boundary {
  margin: 20px;
  padding: 20px;
  border: 1px solid #03CDBA;
  border-radius: 4px;
  background-color: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(10px);
}

.error-message {
  color: #03CDBA;
  font-size: 14px;
  margin-bottom: 10px;
}

.retry-button {
  background: #03CDBA;
  color: #FFFFFF;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.retry-button:hover {
  background: #02a999;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  margin-top: 30px;
}

.service-card {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s ease;
}

.service-card:hover {
  background: rgba(255, 255, 255, 0.08);
}

.service-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.service-content {
  padding: 15px;
}

.service-title {
  color: #03CDBA;
  font-size: 18px;
  margin-bottom: 10px;
}

.service-description {
  color: #FFFFFF;
  font-size: 14px;
  opacity: 0.9;
}

.whatsapp-button {
  position: fixed;
  bottom: 30px;
  right: 30px;
  background: #25D366;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 10px rgba(0,0,0,0.3);
  z-index: 1000;
  transition: transform 0.2s;
  color: white;
  text-decoration: none;
}

.whatsapp-button:hover {
  transform: scale(1.1);
}

.whatsapp-button svg {
  width: 35px;
  height: 35px;
  fill: currentColor;
}

@media screen and (min-width: 769px) {
  body {
    background: transparent;
    position: relative;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: radial-gradient(circle at 50% 50%, 
      rgba(3, 205, 186, 0.7) 0%,
      rgba(2, 19, 42, 0.9) 40%,
      rgba(3, 205, 186, 0.4) 70%,
      rgba(2, 19, 42, 0.9) 100%);
    background-size: 200% 200%;
    filter: blur(80px);
    z-index: -1;
    animation: floatingOrb 30s ease-in-out infinite; /* Changed from previous duration to 30s */
  }

  @keyframes floatingOrb {
    0% {
      background-position: 0% 0%;
      transform: scale(1.2);
    }
    25% {
      background-position: 100% 25%;
      transform: scale(1.1);
    }
    50% {
      background-position: 50% 100%;
      transform: scale(1.3);
    }
    75% {
      background-position: 0% 75%;
      transform: scale(1.1);
    }
    100% {
      background-position: 0% 0%;
      transform: scale(1.2);
    }
  }

  .container {
    margin-top: 40px;
    margin-bottom: 40px;
    min-height: calc(100vh - 80px);
    border-radius: 20px;
    box-shadow: 0 0 40px rgba(0,0,0,0.3);
    position: relative;
    z-index: 1;
  }
}

@media screen and (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;  /* Change to single column */
  }
  
  .service-card {
    max-width: 100%;  /* Ensure cards take full width */
  }
  
  .service-image {
    height: 180px;  /* Slightly reduce image height for mobile */
  }

  .whatsapp-button {
    bottom: 20px;
    right: 20px;
    width: 50px;
    height: 50px;
  }
  
  .whatsapp-button svg {
    width: 30px;
    height: 30px;
  }
}

.creator-section {
  text-align: center;
  margin-top: 40px;
  padding: 20px;
}

.creator-text {
  color: #FFFFFF;
  font-size: 1.2em;
  margin-bottom: 20px;
}

.creator-button {
  display: inline-block;
  background: #03CDBA;
  color: #FFFFFF;
  padding: 16px 32px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.2s ease;
}

.creator-button:hover {
  transform: translateY(-2px);
  background: #02a999;
  box-shadow: 0 4px 15px rgba(3, 205, 186, 0.3);
}

.creator-image {
  max-width: 100%;
  height: auto;
  margin-top: 30px;
  border-radius: 12px;
}

.footer {
  text-align: center;
  margin-top: 30px;
  padding: 20px;
  color: #FFFFFF;
}

.footer p {
  margin: 5px 0;
  opacity: 0.9;
}

.footer .copyright {
  font-size: 0.9em;
  opacity: 0.7;
}
</style>
<script>
window.onerror = function(msg, url, lineNo, columnNo, error) {
  console.error('Error: ' + msg + '\nURL: ' + url + '\nLine: ' + lineNo + '\nColumn: ' + columnNo + '\nError object: ' + JSON.stringify(error));
  showErrorMessage('Algo salió mal. Por favor intenta recargar la página.');
  return false;
};

window.addEventListener('unhandledrejection', function(event) {
  console.error('Unhandled promise rejection:', event.reason);
  if (event.reason && event.reason.status === 500) {
    showErrorMessage('Error de servidor. Por favor intenta más tarde.');
  }
});

function retryLoad(element, src, maxRetries = 3) {
  let attempts = 0;

  function tryLoad() {
    attempts++;
    element.src = src;
  }

  element.onerror = function() {
    if (attempts < maxRetries) {
      setTimeout(tryLoad, Math.pow(2, attempts) * 1000);
    } else {
      console.error(`Failed to load resource after ${maxRetries} attempts:`, src);
      showErrorMessage('No se pudo cargar el recurso. Por favor verifica tu conexión.');
    }
  };

  tryLoad();
}

function showErrorMessage(message) {
  const errorContainer = document.createElement('div');
  errorContainer.className = 'error-boundary';
  errorContainer.innerHTML = `
    <div class="error-message">${message}</div>
    <button class="retry-button" onclick="window.location.reload()">Reintentar</button>
  `;
  
  const container = document.querySelector('.container');
  container.insertBefore(errorContainer, container.firstChild);
}

document.addEventListener('DOMContentLoaded', function() {
  const profileImage = document.querySelector('.profile-image');
  if (profileImage) {
    retryLoad(profileImage, profileImage.src);
  }
  
  document.querySelectorAll('a').forEach(link => {
    link.addEventListener('click', function(e) {
      try {
        new URL(this.href);
      } catch (error) {
        e.preventDefault();
        showErrorMessage('El enlace no es válido.');
      }
    });
  });
});
</script>
</head>
<body>
  <div class="container">
    <header class="profile-header">
      <img class="cover-image"
           alt="Imagen de portada mostrando un escritorio minimalista con computadora y plantas"
           src="https://images.unsplash.com/photo-1499750310107-5fef28a66643?ixlib=rb-4.0.3"
           onerror="this.onerror=null; this.src='data:image/svg+xml,%3Csvg xmlns=\'http://www.w3.org/2000/svg\' width=\'680\' height=\'220\' viewBox=\'0 0 680 220\'%3E%3Crect width=\'680\' height=\'220\' fill=\'%23eee\'/%3E%3C/svg%3E';">
      <img class="profile-image" 
           alt="Foto de perfil circular mostrando una mujer sonriente con estilo profesional" 
           src="https://scontent.fcbb1-1.fna.fbcdn.net/v/t39.30808-6/464219172_122180895764131674_3693171218542176693_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=6ee11a&_nc_ohc=Gzv4OKV3_XAQ7kNvgFIwXVi&_nc_zt=23&_nc_ht=scontent.fcbb1-1.fna&_nc_gid=AWpPeC-oBmfDfgd5AHAhADw&oh=00_AYAOYiZ121AEbt5kLfKrH-9QNJiujjnTztlPK2CUCKiTUw&oe=673A14C7"
           onerror="this.onerror=null; this.src='data:image/svg+xml,%3Csvg xmlns=\'http://www.w3.org/2000/svg\' width=\'120\' height=\'120\' viewBox=\'0 0 24 24\'%3E%3Cpath fill=\'%23ccc\' d=\'M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z\'/%3E%3C/svg%3E';">
      <h1 class="profile-name">Malelemdz</h1>
      <p class="profile-bio">¡Hola! Mi nombre es María. Te doy la bienvenida a mi espacio digital 💜</p>
    </header>

    <div class="social-links">
      <a href="https://www.tiktok.com/@malelemdz" class="social-icon">
        <svg viewBox="0 0 24 24" fill="#FFFFFF">
          <path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.2 1.74 2.89 2.89 0 0 1 2.31-4.64 2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.05A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43v-7a8.16 8.16 0 0 0 4.77 1.52v-3.4a4.85 4.85 0 0 1-1-.1z"/>
        </svg>
      </a>
      
      <a href="https://www.instagram.com/malelemdz" class="social-icon">
        <svg viewBox="0 0 24 24" fill="#FFFFFF">
          <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
        </svg>
      </a>

      <a href="https://www.facebook.com/malelemdz" class="social-icon">
        <svg viewBox="0 0 24 24" fill="#FFFFFF">
          <path d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.192-1.333 1.115-1.333h2.885v-5h-3.808c-3.596 0-5.192 1.583-5.192 4.615v3.385z"/>
        </svg>
      </a>

      <a href="https://www.youtube.com/@malelemdz" class="social-icon">
        <svg viewBox="0 0 24 24" fill="#FFFFFF">
          <path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"/>
        </svg>
      </a>
    </div>

    <div class="services-grid">
      <div class="service-card">
        <img class="service-image" 
             alt="Branding design concept with colorful logo sketches and brand elements" 
             src="https://images.unsplash.com/photo-1524419986249-348e8fa6ad4a?ixlib=rb-4.0.3"
             width="300" height="200">
        <div class="service-content">
          <h3 class="service-title">Creación de marca</h3>
          <p class="service-description">Desarrollo de identidades visuales únicas y memorables que conectan con tu audiencia ideal.</p>
        </div>
      </div>

      <div class="service-card">
        <img class="service-image" 
             alt="Social media content creation workspace with smartphone and creative elements" 
             src="https://images.unsplash.com/photo-1611162616475-46b635cb6868?ixlib=rb-4.0.3"
             width="300" height="200">
        <div class="service-content">
          <h3 class="service-title">Diseño para redes sociales</h3>
          <p class="service-description">Contenido visual atractivo y estratégico para impulsar tu presencia en redes sociales.</p>
        </div>
      </div>

      <div class="service-card">
        <img class="service-image" 
             alt="Video editing workspace with multiple monitors showing editing software" 
             src="https://images.unsplash.com/photo-1574717024453-354b9f080549?ixlib=rb-4.0.3"
             width="300" height="200">
        <div class="service-content">
          <h3 class="service-title">Edición de video</h3>
          <p class="service-description">Edición profesional de videos para contar tu historia de manera impactante y memorable.</p>
        </div>
      </div>

      <div class="service-card">
        <img class="service-image" 
             alt="Professional photography setup with camera and lighting equipment" 
             src="https://images.unsplash.com/photo-1516035069371-29a1b244cc32?ixlib=rb-4.0.3"
             width="300" height="200">
        <div class="service-content">
          <h3 class="service-title">Fotografía</h3>
          <p class="service-description">Capturando momentos y productos con un enfoque artístico y profesional.</p>
        </div>
      </div>

      <div class="service-card">
        <img class="service-image" 
             alt="Social media management workspace with analytics dashboard" 
             src="https://images.unsplash.com/photo-1432888622747-4eb9a8efeb07?ixlib=rb-4.0.3"
             width="300" height="200">
        <div class="service-content">
          <h3 class="service-title">Social Media</h3>
          <p class="service-description">Gestión integral de redes sociales para aumentar tu alcance y engagement.</p>
        </div>
      </div>

      <div class="service-card">
        <img class="service-image" 
             alt="Digital invitation design concept with tablet showing elegant templates" 
             src="https://images.unsplash.com/photo-1544913776-90c1223073a0?ixlib=rb-4.0.3"
             width="300" height="200">
        <div class="service-content">
          <h3 class="service-title">Invitaciones digitales</h3>
          <p class="service-description">Diseños personalizados para tus eventos especiales con un toque moderno y elegante.</p>
        </div>
      </div>
    </div>
    
    <div class="creator-section">
      <p class="creator-text">Si eres creador de contenido descarga recursos aquí</p>
      <a href="https://beacons.ai/malelemdz" class="creator-button" target="_blank" rel="noopener noreferrer">
        Descargar recursos
      </a>
      <img 
        src="https://cdn.beacons.ai/user_content/zck0xzJr5EcU99K4ZggyudiHMaO2/referenced_images/ca04e8b6-1741-4c70-ab33-017b5019835c__link-in-bio__image-block__home__5eddde6f-1270-417a-bb33-cee71b6c4d30__82fa93b9-bec6-44d3-bcb2-7baf14f21807.jpg?t=1730095122041"
        alt="Recursos para creadores de contenido"
        class="creator-image"
        width="600"
        height="400"
      >
    </div>
    <div class="footer">
      <p>¡Gracias por ver!</p>
      <p class="copyright">© 2024 Malelemdz. Todos los derechos reservados.</p>
    </div>
  </div>
  <a href="https://wa.me/549XXXXXXXXXX" class="whatsapp-button" target="_blank" rel="noopener noreferrer">
    <svg viewBox="0 0 24 24">
      <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/>
    </svg>
  </a>
</body>
</html>
