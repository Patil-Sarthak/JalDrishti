# JalDrishti

Technologies
Hardware: ESP32 dev board · ultrasonic or pressure level sensor · two-electrode EC/TDS probe · tipping-bucket rain gauge · SX1276 LoRa radio · microSD · 6 V solar panel, charge controller, 3.7 V Li-ion cell · IP65 enclosure · stainless sensor cable.
Firmware: Arduino / C++ on the ESP32 core — deep sleep between readings, RTC timestamps, SD logging, LoRaWAN OTAA join, Wi-Fi fallback, OTA update.
Backend: Firebase or Node + PostgreSQL for readings by well; Python (pandas, numpy) for the water budget and percentile alerts; a scheduled job per village each month.
Front end: Android app (Kotlin or Flutter) for the farmer; a React web dashboard for the panchayat; a shared alert list both can see.
Network: The Things Network community gateway, or one village gateway owned by the panchayat; no cellular data plan needed at the node.
Implementation plan
1. Bench: three sensors + ESP32, readings in the serial monitor, then in the database.
2. Calibrate the level sensor against a measuring tape; log the offset in firmware.
3. Seal the enclosure, mount the panel, drop the cable into one open well.
4. Run one week through a monsoon shower; check for gaps and condensation.
5. Load three years of IMD rainfall and switch on the budget and the alert.
6. Scale to twelve wells in one panchayat for one season, with the block office watching.


One reading, as it reaches the cloud
{"well": "KH-07", "ts": "2026-11-21T06:15+05:30", "depth_m": 8.42, "ec_us": 1180, "rain_mm": 0.0, "batt_v": 3.91}
Depth is the headline number; EC tells us whether the water is turning saline as it falls; the battery field is the heartbeat.

<img width="33" height="624" alt="image" src="https://github.com/user-attachments/assets/57d92be2-acd5-4428-9910-827ac2ab5c0f" />

<img width="1803" height="112" alt="image" src="https://github.com/user-attachments/assets/d29f35c2-6b55-45f0-8e2a-f7233a681b28" />

<img width="3643" height="707" alt="image" src="https://github.com/user-attachments/assets/725221f7-da8b-4847-a120-b6f4bdde5b93" />


<img width="3048" height="1735" alt="image" src="https://github.com/user-attachments/assets/07c76d35-1946-477e-94c2-2e0885998616" />
