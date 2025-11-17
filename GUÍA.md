# Guía de instalación de Pi-hole

Antes de empezar este mini proyecto lo he hecho con mi Raspberry Pi 5, de 8GB de RAM y 128GB de memoria microSD.

## 📌 Requisitos previos

* Un dispositivo con **Linux** (Raspberry Pi OS, Debian, Ubuntu).
* Acceso a **terminal** y permisos de superusuario.
* Conexión a la red local.
* (Opcional) Router configurado para usar Pi-hole como DNS.

## 🛠️ Instalación estándar

Pi-hole ofrece un script automatizado que facilita la instalación.

## 0. Configurar IP fija.

Para que Pi-hole pueda funcionar es obligatorio tener un IP fija, para esto tendremos que escoger una IP fuera del rango de nuestro DNS. Una vez hecho esto podemos empezar.

### 1. Actualiza el sistema

```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Instala Pi-hole con el script oficial

```bash
curl -sSL https://install.pi-hole.net | bash
```

### 3. Sigue las instrucciones del asistente

Selecciona:

* El proveedor de DNS que quieras.
* Un modelo de privacidad para FTL.
* Habilitar query logging.

## 🌐 Acceso a la interfaz web

Después de la instalación, Pi-hole estará disponible en:

```
http://<IP-de-tu-dispositivo>/admin
```

## 🔐 Recuperar o cambiar la contraseña de administrador

```bash
sudo pihole setpassword
```

## 🔄 Actualización de Pi-hole

```bash
pihole -up
```

## Utilizar pi-hole como DNS.

Para que todos los dispositivos de nuestra red estén protegidos de anuncios y malware, lo usual es poner la IP de nuestro router en el navegador y editar el DNS, poniendo la IP del dispositivo donde está pi-hole en su lugar.
Si existe el DNS secundario y no te deja dejarlo vacío, vuelve a poner la IP donde está alojado pi-hole.

## 🧪 Verificación del funcionamiento

* Abre la interfaz web y revisa las estadísticas.

## 📚 Recursos adicionales

* Documentación oficial: [https://docs.pi-hole.net/](https://docs.pi-hole.net/)

---

¡Ya has instalado pi-hole!
