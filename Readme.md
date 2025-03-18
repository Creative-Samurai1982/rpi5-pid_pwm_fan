raspberry-pi-pid-pwm-fan
===
A Python script to monitor CPU temperature and adjust fan speed using PID.
Originaly I used simular code to run a fan on my Rpi 4, but since updating to a Rpi 5,
my original code wouldn't work on the Rpi 5, so i adapted my code.
Enjoy

## Required Python Packages

Update Linux packages:
```
sudo apt-get update
```

Install Python 3 if not available:
```
sudo apt-get install python3.6
```

Install gpiozero package
```
sudo apt install python3-gpiozero
```

## Local Test

You can test if the Python script works by running:
```
python3 pid_pwm_fan.py
```

## Copy Files

### Copy pid_pwm_fan.py Python Script

```
sudo cp pid_pwm_fan.py /usr/local/bin/pid_pwm_fan.py
sudo chmod +x pid_pwm_fan.py
```

### Copy pid_pwm_fan Shell Script

```
sudo cp pid_pwm_fan /etc/init.d/pid_pwm_fan
sudo chmod +x pid_pwm_fan
```

### Run update-rc

```
sudo update-rc.d pid_pwm_fan defaults
```

### Verify

```
/etc/init.d/pid_pwm_fan start
```

If you see error like ```-bash: /etc/init.d/pid_pwm_fan: /bin/sh^M: bad interpreter:
No such file or directory```, it means the bash file format is incorrect.

To fix this:
```
vi /etc/init.d/pid_pwm_fan
```
then type ```:set ff=unix```, then save with ```wq!```.

### Reboot

```
sudo reboot
```
