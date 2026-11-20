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

<img width="874" height="661" alt="image" src="https://github.com/user-attachments/assets/3201ca59-4c92-46b6-9fd2-f1a1c5f0f641" />


