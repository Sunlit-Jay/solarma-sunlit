# solarman-sunlit
Modified Solarman integration for Home Assistant with register 53 support for active power regulation

> **Important Notice**: This repository is a modified version of [davidrapan/ha-solarman](https://github.com/davidrapan/ha-solarman). The original code copyright belongs to the respective author. This modification is made solely to address specific device compatibility issues.

## 🔧 Modification Reason and Technical Explanation

In the original Solarman component, the "Active Power Regulation" feature that controls the power output of Deye inverters corresponds to the inverter's **Register 40** (address 0x0028). Through practical testing, we discovered:

- Register 40 does not support setting the power output to **0%**
- The minimum settable value is only 1%, making zero feed-in impossible to achieve
- The inverter's **Register 53** (address 0x0035) supports adjustment down to 0% output
- Register 53 is more suitable for precise power control requirements
