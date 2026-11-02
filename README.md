# Emudhroll
By exploiting the eMudhra CA compromise, device management requests are intercepted and spoofed to unenroll managed Chromebooks. 

## Setup

1. Clone this repo:
   git clone https://github.com/g00fle/Emudhroll && cd Emudhroll
2. Install requirements:
   pip install -r requirements.txt
3. Run the proxy:
   python main.py
4. Permanent unenrollment mode:
   python main.py --permanent
5. Re-enroll:
   python main.py --enroll

The proxy listens on port 8080.

## Unenroll

1. Powerwash the Chromebook.
2. On the Welcome OOBE screen, connect to Wi-Fi and open its proxy settings.
3. Set to Manual proxy configuration.
4. Enable Use the same proxy for all protocols.
5. Enter your computer's IP and port 8080.
6. Continue through OOBE and it should unenroll

## Re-enroll (--enroll)

1. Run: python main.py --enroll
2. Enter the stable device secret (hex) when prompted (this is obtained via entering devmode and running vpd -l as root in vt2)
3. On powerwash, it will successfully reenroll
