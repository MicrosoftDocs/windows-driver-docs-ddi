---
UID: TP:biometric
ms.assetid: 5af9b578-0fef-3edc-b459-8e62ce9c45f8
ms.author: windowsdriverdev
ms.date: 04/20/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Biometric

## -description

Overview of the Biometric technology.

To develop Biometric, you need these headers:

 * [winbio_ioctl.h](..\winbio_ioctl\index.md)
 * [winbio_types.h](..\winbio_types\index.md)

For the programming guide, see [Biometric](https://docs.microsoft.com/en-us/windows-hardware/drivers/biometric).

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WINBIO_BIR structure](..\winbio_types\ns-winbio_types-_winbio_bir.md) | The WINBIO_BIR structure is the root of the BIR (Biometric Information Record). It contains the size and offset of any other data elements in the BIR. |
| [_WINBIO_BIR_DATA structure](..\winbio_types\ns-winbio_types-_winbio_bir_data.md) | The WINBIO_BIR_DATA structure contains the location and size of a block in a BIR. The offset is measured from the beginning of the WINBIO_BIR structure. |
| [_WINBIO_BIR_HEADER structure](..\winbio_types\ns-winbio_types-_winbio_bir_header.md) | The WINBIO_BIR_HEADER structure contains the Common Biometric Exchange File Format (CBEFF) Patron Format A information that describes the rest of the BIR. |
| [_WINBIO_BLANK_PAYLOAD structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_blank_payload.md) | The IOCTL_BIOMETRIC_RESET and IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTLs return the WINBIO_BLANK_PAYLOAD structure as output. |
| [_WINBIO_CALIBRATION_INFO structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_calibration_info.md) | The IOCTL_BIOMETRIC_CALIBRATE IOCTL returns the WINBIO_CALIBRATION_INFO structure as output. |
| [_WINBIO_CAPTURE_DATA structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_capture_data.md) | The IOCTL_BIOMETRIC_CAPTURE_DATA IOCTL returns the WINBIO_CAPTURE_DATA structure as output. |
| [_WINBIO_CAPTURE_PARAMETERS structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_capture_parameters.md) | The IOCTL_BIOMETRIC_CAPTURE_DATA IOCTL uses the WINBIO_CAPTURE_PARAMETERS structure as input. |
| [_WINBIO_DATA structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_data.md) | The WINBIO_DATA structure specifies data in IOCTL payloads. |
| [_WINBIO_DIAGNOSTICS structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_diagnostics.md) | The IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL returns the WINBIO_DIAGNOSTICS structure as output. |
| [_WINBIO_GET_INDICATOR structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_get_indicator.md) | The WINBIO_GET_INDICATOR structure is the OUT payload for IOCTL_BIOMETRIC_GET_INDICATOR. |
| [_WINBIO_REGISTERED_FORMAT structure](..\winbio_types\ns-winbio_types-_winbio_registered_format.md) | The WINBIO_REGISTERED_FORMAT structure specifies a biometric data format. |
| [_WINBIO_SENSOR_ATTRIBUTES structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_sensor_attributes.md) | The IOCTL_BIOMETRIC_GET_ATTRIBUTES structure returns the WINBIO_SENSOR_ATTRIBUTES structure as output. |
| [_WINBIO_SET_INDICATOR structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_set_indicator.md) | The WINBIO_SET_INDICATOR structure is the IN payload for IOCTL_BIOMETRIC_SET_INDICATOR. |
| [_WINBIO_SUPPORTED_ALGORITHMS structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_supported_algorithms.md) | The WINBIO_SUPPORTED_ALGORITHMS structure is the OUT payload for IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS. |
| [_WINBIO_UPDATE_FIRMWARE structure](..\winbio_ioctl\ns-winbio_ioctl-_winbio_update_firmware.md) | The WINBIO_UPDATE_FIRMWARE structure is the IN payload for IOCTL_BIOMETRIC_UPDATE_FIRMWARE. |
| [_WINBIO_VERSION structure](..\winbio_types\ns-winbio_types-_winbio_version.md) | The WINBIO_VERSION structure describes major and minor version information for a WBDI driver. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_BIOMETRIC_CALIBRATE IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_calibrate.md) | The IOCTL_BIOMETRIC_CALIBRATE IOCTL directs the driver to perform any necessary steps to calibrate the device for use. |
| [IOCTL_BIOMETRIC_CAPTURE_DATA IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_capture_data.md) | The IOCTL_BIOMETRIC_CAPTURE_DATA IOCTL directs the driver to retrieve the next scan of biometric data. This call should put the device into capture mode.Vendor-supplied WBDI drivers must support IOCTL_BIOMETRIC_CAPTURE_DATA. |
| [IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_attributes.md) | The IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL returns a structure that contains a set of attributes for the sensor. Vendor-supplied WBDI drivers must support this IOCTL. |
| [IOCTL_BIOMETRIC_GET_INDICATOR IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_indicator.md) | The IOCTL_BIOMETRIC_GET_INDICATOR IOCTL directs the driver to retrieve the status of the indicator light. This IOCTL is optional. |
| [IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_sensor_status.md) | The IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL tells the driver to perform any necessary steps to collect the current operating status of the device. Vendor-supplied WBDI drivers must support this IOCTL. |
| [IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_supported_algorithms.md) | The IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS IOCTL retrieves a list of cryptographic hash algorithms that are supported by the device. This IOCTL is optional. |
| [IOCTL_BIOMETRIC_RESET IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_reset.md) | The IOCTL_BIOMETRIC_RESET IOCTL resets the device to a known or idle state, according to the current power state. Vendor-supplied WBDI drivers must support this IOCTL. |
| [IOCTL_BIOMETRIC_SET_INDICATOR IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_set_indicator.md) | The IOCTL_BIOMETRIC_SET_INDICATOR IOCTL directs the driver to update the status of the indicator light. |
| [IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTL](..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_update_firmware.md) | The IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTL tells the driver to update the firmware for the device with the given firmware image. This IOCTL is optional. |
