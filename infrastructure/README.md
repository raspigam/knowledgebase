# Infrastructure

## Internet access

Please share experience on plans, reliability and speed here. It would be nice to list the existing realistic options here.

## Local (sometimes offline) access to online content

Using a RACHEL (Rural Area Community Hotspot for Education and Learning) we could mitigate part of the trouble from the internet connection not being reliable.

## Computer Lab server setup

- Internet proxy (to keep bandwidth to and from the internet low and repeated access fast)
- Khan Academy server (KALite - https://learningequality.org/ka-lite - a huge repository of learning content that can be made available offline), maybe best as separate RACHEL server setup, see http://rachelfriends.org/rachel-pi-howto.html

## Power management

Mains power, however available in many areas in the Gambia, is often unreliable in the sense that many outages occur, sometimes spanning several hours. So it pays off to search for locally maintainable, cheapest, most robust ways of overcoming this.

The Raspberry Pi configuration demonstrated in Sanyang April 2017 uses a UPS board ("HAT") to be able to safely shutdown within minutes after a power outage. The board ("UPSPiCo HW V3.0") is quite versatile, e.g. it also features fan (cooling) control. The shipped batteries (450mAh) don't provide enough power to keep the computer alive for long, in particular because the in this setup included touch screen needs to be powered too. The higher capacity battery packs (4000mAh) we tried to order were unfortunately temporarily out of stock.

On the GitHub pages of Rob Jones (Craic Computing) at https://github.com/craic/pi_power one can find quite detailed plans on how to create a low cost power management solution.

An alternative approach, starting from the simplest working electronics solution possible, is shown at http://homediyelectronics.com/projects/raspberrypi/ups.

https://hackaday.io/project/25116-single-cell-li-ion-powered-ups-for-raspberry-pi

