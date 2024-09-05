# Hypervisor

Bindeglied zwischen dem Host und den VMs mit ihren Gast-Betriebssystemen ist ein Hypervisor. Ein Hypervisor ist eine Software mit der die VMs verwaltet und die Hardware-Ressourcen des Hosts (z.B. CPU, RAM und Festplattenspeicher) auf die vorhandenen VMs verteilt werden. Auf einem Host können VMs mit unterschiedlichen Betriebssystemen und Versionen (z.B. Windows 10, Windows 11, Ubuntu, Debian) ausgeführt werden.

## Arten
Es gibt zwei Arten von Hypervisoren, die beide relevant sind: Typ 1 und Typ 2.

### Typ 1

![image_3.png](image_3.png)

| Funktionsweise        | Läuft direkt auf der physischen Hardware des Hosts. |
|-----------------------|-----------------------------------------------------|
| Vorteile              | - Hohe Leistung und Effizienz                       |
|                       | - Direkte Hardwarezugriffe                          |
| Nachteile             | - Komplizierte Einrichtung                          |
|                       | - Benötigt Treiber für alle Hardware-Komponenten    |
| Einsatz in der Praxis | Ideal für Server-Umgebungen in Rechenzentren        |
| Beispiele             | - Hyper-V (Microsoft)                               |
|                       | - vSphere Hypervisor ehemals ESX/ESXi (VMware)      |
|                       | - XenServer (Citrix)                                |
|                       | - PowerVM (IBM)                                     |
|                       | - LPAR und PR/SM (IBM)                              |
|                       | - Proxmox VE (Proxmox)                              |
|                       | - KVM - Kernel-based Virtual Machine (Open Source)  |
|                       | - QEMU - Quick Emulator (Freie Software)            |

### Typ 2

![image_4.png](image_4.png)

| Funktionsweise        | Läuft als Anwendung auf einem bestehenden Betriebssystem (Host-OS). |
|-----------------------|---------------------------------------------------------------------|
| Vorteile              | - Einfach einzurichten und zu verwalten                             |
|                       | - Nutzt bestehende Treiber des Host-OS                              |
| Nachteile             | - Abhängigkeit von der Leistung des Host-OS                         |
|                       | - Potenzieller Overhead                                             |
| Einsatz in der Praxis | Geeignet für Entwicklungs- und Testumgebungen sowie für Endnutzer   |
| Beispiele             | - VMware Workstation for Windows (Broadcom)                         |
|                       | - VMware Fusion Player for Mac (Broadcom)                           |
|                       | - Windows Virtual PC (Microsoft)                                    |
|                       | - VirtualBox (Oracle)                                               |
|                       | - Parallels Workstation                                             |
