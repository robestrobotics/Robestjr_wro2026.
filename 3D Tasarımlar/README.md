========================================================================================
                      ROBOT MOBİL ŞASİ VE SENSÖR DEVRE ŞEMASI
========================================================================================

    [ PİL YATAĞI (4xAA)]                     [ MESAFE SENSÖRÜ (HC-SR04) ]
     ┌───────────────┐                             ┌────────────────┐
     │  (+) Kırmızı  │──────┐                      │ VCC   TRIG  ECHO  GND │
     │  (-) Siyah    │──┐   │                      └──┬─────┬─────┬─────┬──┘
     └───────────────┘  │   │                         │     │     │     │
                        │   ▼                         │     │     │     │
                        │ ┌──────────────┐            │     │     │     │
                        │ │ PUSH BUTTON  │            │     │     │     │
                        │ │ (Ana Şalter) │            │     │     │     │
                        │ └──────┬───────┘            │     │     │     │
                        │        │ Jumper             ▼ 5V  ▼     │     ▼
                        │        ▼                    Pi    Pi    │   Pi GND
                        │ ┌──────────────┐           (5V) (GPIO5) │
                        │ │ L298N SÜRÜCÜ │                        │
                        │ │              │                        ▼
                        │ │ [12V] Vidası │◄───────────────────────┘
                        │ │              │     [ VOLTAJ BÖLÜCÜ DİRENÇ Y KAVŞAĞI ]
                        │ │ [GND] Vidası │◄──┐                  
                        │ └──────────────┘   │   Sol (Beyaz Kablo)   : Echo Pininden Gelen (5V)
                        │                    │   Orta (Kahve Kablo)  : Raspberry Pi [GPIO 6] (3.3V)
                        └────────────────────┼───Sağ (Siyah Kablo)   : Ortak GND Hattı
                                             │
                                             │
                                             ▼
                                  ┌────────────────────┐
                                  │ RASPBERRY PI PINOUT│
                                  │                    │
                                  │  [5V]  ────────────┼─── (Sensör VCC)
                                  │  [GND] ────────────┼─── (Sensör GND)
                                  │  [GPIO 5] ─────────┼─── (Sensör TRIG)
                                  │                    │
                                  │  [GPIO 6] ─────────┼─── (Y Kavşağı - Orta Kahverengi)
                                  │  [GND] ────────────┴─── (L298N GND Vidasına Köprü)
                                  └────────────────────┘

========================================================================================
NOT: Tüm eksi (GND) hatları L298N sürücünün orta klemensindeki GND vidasında birleşmiştir.
========================================================================================
