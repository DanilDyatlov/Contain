sudo apt update
sudo apt install lxc-utils

Смотрим
lxs storage list
lxc network list
ip a

Создаем
lxc-create -n test123 -t ubuntu --создаем контейнер
lxc-start -n test123 -- запускаем
lxc-attach -n teat123 -- войдем в него
free -m —проверяем пямаять
exit -- выходим
lxc-stop -n test123 - -закрываем

nano /var/lib/lxc/test123/config-открываем
lxc.rootfs.path = dir:/var/lib/lxc/test1234/rootfs — путь
lxc.uts.name = test1234 -- имя

Network configuration — Конфегурация сети
.
.
.
lxc.cgroup2.memory.max = 256M -- ограничиваем(В режиме Вставка делаем запись)

lxc-start -n test123 -- запускаем
lxc-attach -n teat123 -- войдем в него
free -m -- проверяем пямаять
!!!Видим что наше ограничение работает!!!

Установка ЛКС

apt-get install lxc debootstrap bridge-utils lxc-templates
apt-get install lxd-installer
lxd init(Здесь просто нажимаем на Enter что уствновились значения по умолчанию)
Проверяем
lxc storage list
lxc storage list
И создаем контейнер