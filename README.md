# DNS Maestro-Esclavo

Este proyecto configura un sistema de DNS utilizando BIND9 en un entorno de virtualización con Vagrant. Se establecen servidores DNS maestro y esclavo, permitiendo la resolución de nombres y la transferencia de zonas.

## Tecnologías Utilizadas
- [BIND9](https://www.isc.org/bind/) para la gestión de DNS.
- [Vagrant](https://www.vagrantup.com/) para la creación y gestión de entornos virtualizados.
- [Debian](https://www.debian.org/) como sistema operativo para las máquinas virtuales.

## Estructura del Proyecto
```
proyecto-dns/
├── Vagrantfile
├── tierra/
│   ├── named.conf.local
│   ├── named.conf.options
│   ├── db.sistema.test
│   └── db.192.168.57
└── venus/
    ├── named.conf.local
    └── named.conf.options
```

## Instalación
1. Clona el repositorio:
   ```bash
   git clone https://github.com/IsmaelManz26/DnsMaestro-Esclavo.git
   ```
   
2. Navega al directorio del proyecto:
   ```bash
   cd DnsMaestro-Esclavo
   ```
   
3. Inicia las máquinas virtuales usando Vagrant:
   ```bash
   vagrant up
   ```

## Configuración
- **Servidor Maestro (Tierra)**
  - IP: `192.168.57.103`
  - Archivos de configuración: `named.conf.local`, `named.conf.options`, `db.sistema.test`, `db.192.168.57`
  
- **Servidor Esclavo (Venus)**
  - IP: `192.168.57.102`
  - Archivos de configuración: `named.conf.local`, `named.conf.options`

## Funcionalidades
- Resolución de nombres A, PTR y MX.
- Transferencia de zonas entre el servidor maestro y esclavo.
- Configuración de registros de alias (CNAME) y registros NS.

## Comprobaciones
- Se realizaron pruebas para verificar que el servidor maestro y esclavo respondían a las mismas consultas DNS.
- Se verificó la correcta transferencia de la zona mediante la consulta AXFR.

## Contribuciones
Las contribuciones son bienvenidas. Si deseas contribuir, por favor abre un issue o envía un pull request.

## Licencia
Este proyecto está licenciado bajo la [Licencia MIT](LICENSE).
