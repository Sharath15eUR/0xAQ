# Module 2 – Network Performance Measurement Tools Assignment - Wireshark 

1. Install Wireshark, take capture on WiFi interface ( my interface - wlp0s20f3)
   ![wifi interface](https://github.com/Sharath15eUR/0xAQ/assets/88236255/b0481bdd-3027-481c-ba73-616019795490)
2.Identify the beacon frame using filter.
  > To view beacon frames interface must be in monitor mode (sudo airmon-ng start wlp0s20f3)
  wireshark will show wlp0s20f3mon now start capturing. then filter them using wlan.fc.type_subtype == 0x8

  ![beacon frame](https://github.com/Sharath15eUR/0xAQ/assets/88236255/72f02e03-9df7-4999-af76-961a31d5ebc1)

3. Apply filters to view specific packet.
   >tcp.port == 443 is filter to show only https packets
   
   ![filter](https://github.com/Sharath15eUR/0xAQ/assets/88236255/235129b1-92bf-446d-af69-20f32c0f775b)
   
5. Point out ethernet and 802.11 frames
   ![wifi capture](https://github.com/Sharath15eUR/0xAQ/assets/88236255/146b5855-af27-4bb5-8501-4ade4a7ea32a)