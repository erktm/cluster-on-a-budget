# cluster-on-a-budget

This project will be a short documentation of how I built my small 2-node Raspberry Pi 5 k3s cluster on a small budget with a minimal redundant setup.

My main goal is to get familiar with Kubernetes fundamentals like objects, networking, and storage. I believe that there are many people out there who want the same, which is why I’m sharing this with you.

### Right now, this is what the cluster looks like:

![](pictures/full_application.jpeg)

As you can see, there are already three slots for an additional Raspberry Pi, which I plan to add once I’m more familiar with the current setup.

## List of Hardware Components

| Name                                | Quantity | Link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-------------------------------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Raspberry Pi 5, 8GB RAM             | 2        | [berrybase.de](https://www.berrybase.de/raspberry-pi-5-8gb-ram?utm_source=google&utm_medium=cpc&gad_source=1&gbraid=0AAAAADSQJK6LI8yI-fNnIvGFkF7u8Rj6d&gclid=CjwKCAjwwe2_BhBEEiwAM1I7sVc4W97qqFND67wHfhJSrcIpbKqMFOGu4-BOTeYzwWLdp0nS_3l7lRoCyA0QAvD_BwE)                                                                                                                                                                                                                                                                                                                                 |
| GeeekPi P33 M.2 NVME M-Key PoE+ Hat | 2        | [amazon.de](https://www.amazon.de/dp/B0D8J7B47N?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Fanxiang M.2 SSD 512GB              | 2        | [amazon.de](https://www.amazon.de/dp/B0B55R7PYB?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 2U DAP rack panel                   | 1        | [musicstore.de](https://www.musicstore.de/de_DE/EUR/DAP-2-HE-Rackblende-f-Modulsystem-10-Segmente-MP-1/art-PAH0017160-000)                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| TP-Link TL-SG1005P PoE Switch       | 1        | [amazon.de](https://www.amazon.de/dp/B0763TGBTS?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| SanDisk 32 GB micro SD card         | 1        | [amazon.de](https://www.amazon.de/SanDisk-microSDHC-Speicherkarte-SD-Adapter-App-Leistung/dp/B08GY9NYRM/ref=sr_1_10?__mk_de_DE=ÅMÅŽÕÑ&crid=2Y06TNE22W65A&dib=eyJ2IjoiMSJ9.wURXrQCPkQt61NVEdL51J61A-TqAQX5eZf7FvhzTxR4haI2kQBZbzO7EcXDhI5WIotIxFnO-IsGhkhwDt0kYmHzFIYIbX6OiKXFFYs56u70AdTT-NyCn9RBso5w9b_wR7va4yOQawWRRK3ODT2m8c7rerbYhi9nl4C_Xnafbsza2uLPjCrvvhxjDJLyAOjPE4NxH60mdSwbWqpAq-mrMByaaNqM3sFmQt6UdWNpccw4.QXt6SAgkGFwJGMmwD-FAF4IehhT2bWYV9SvJzFTUVfc&dib_tag=se&keywords=micro+sd+karte+sandisk&qid=1744556517&sprefix=micro+sd+karte+sandisk%2Caps%2C121&sr=8-10)           |

### Total costs: 395€ / 448$

## Printables

| Name                      | Quantity | Link                                                                                                                                                                                                                                                      |
|---------------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TL-SG1005P Rack Mount     | 1        | [berrybase.de](https://www.berrybase.de/raspberry-pi-5-8gb-ram?utm_source=google&utm_medium=cpc&gad_source=1&gbraid=0AAAAADSQJK6LI8yI-fNnIvGFkF7u8Rj6d&gclid=CjwKCAjwwe2_BhBEEiwAM1I7sVc4W97qqFND67wHfhJSrcIpbKqMFOGu4-BOTeYzwWLdp0nS_3l7lRoCyA0QAvD_BwE) |
| Raspberry Pi 5 Rack-Mount | 2        | [printables.com](https://www.printables.com/model/780897-tl-sg1005p-rack-mount?lang=de)                                                                                                                                                                   |

## The Setup

First, after assembling the components, I had to create a bootable SD card with [Ubuntu Desktop](https://ubuntu.com/desktop) on my PC to boot the Raspberry Pis.
Later, I’ll need Ubuntu Desktop to make the NVMe drives bootable for the Raspberry Pis.

To make the SD card and NVMe's bootable, I use the [Raspberry Pi Imager](https://www.raspberrypi.com/software/).

![](pictures/ubuntu-desktop-boot.png)

After completing the process, you just need to insert the SD card into the first Raspberry Pi.
