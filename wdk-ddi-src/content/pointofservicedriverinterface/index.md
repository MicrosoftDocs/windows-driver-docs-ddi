---
UID: NA:pointofservicedriverinterface
ms.assetid: d8f3ae77-dab5-34d2-a88f-30aa2fd8701d
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Pointofservicedriverinterface.h header



This header is used by Point of Service (POS). For more information, see
- [Point of Service (POS)](../_pos/index.md)

Pointofservicedriverinterface.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_LineDisplayCharacterData structure](ns-pointofservicedriverinterface-_linedisplaycharacterdata.md) | This structure is not implemented. |
| [_LineDisplayGlyphDefinitionData structure](ns-pointofservicedriverinterface-_linedisplayglyphdefinitiondata.md) | This structure is not implemented. |
| [_LineDisplaySetBitmapData structure](ns-pointofservicedriverinterface-_linedisplaysetbitmapdata.md) | This structure is not implemented. |
| [_LineDisplaySetDescriptorData structure](ns-pointofservicedriverinterface-_linedisplaysetdescriptordata.md) | This structure is not implemented. |
| [_LineDisplayWindowDisplayBitmapData structure](ns-pointofservicedriverinterface-_linedisplaywindowdisplaybitmapdata.md) | This structure is not implemented. |
| [_MSR_AUTHENTICATE_DEVICE structure](ns-pointofservicedriverinterface-_msr_authenticate_device.md) | This structure provides the authentication information used to authenticate a device. |
| [_MSR_DATA_RECEIVED structure](ns-pointofservicedriverinterface-_msr_data_received.md) | This structure contains the data read from a swiped magnetic stripe card. |
| [_MSR_DEAUTHENTICATE_DEVICE structure](ns-pointofservicedriverinterface-_msr_deauthenticate_device.md) | This structure provides the information necessary to deauthenticate the device. |
| [_MSR_ERROR_EVENT structure](ns-pointofservicedriverinterface-_msr_error_event.md) | This structure contains the error data that is passed to the MagneticStripeReaderErrorOccured event. |
| [_MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA structure](ns-pointofservicedriverinterface-_msr_retrieve_device_authentication_data.md) | This structure contains authentication information retrieved from the device. |
| [_MSR_SUPPORTED_CARD_TYPES structure](ns-pointofservicedriverinterface-_msr_supported_card_types.md) | This structure defines the types of magnetic stripe cards supported by the reader. |
| [_MSR_UPDATE_KEY structure](ns-pointofservicedriverinterface-_msr_update_key.md) | This structure contains the information necessary to set a new encryption key. |
| [_PosBarcodeScanDataTypeData structure](ns-pointofservicedriverinterface-_posbarcodescandatatypedata.md) | This structure describes a buffer of barcode symbologies supported by the driver. |
| [_PosBarcodeScannerCapabilitiesType structure](ns-pointofservicedriverinterface-_posbarcodescannercapabilitiestype.md) | This structure defines the type of scanner capabilities that a device supports such as whether the device supports statistics reporting and image preview. |
| [_PosBarcodeScannerDataReceivedEventData structure](ns-pointofservicedriverinterface-_posbarcodescannerdatareceivedeventdata.md) | This structure contains the scanned data that is passed to the BarcodeScannerDataReceived event. |
| [_PosBarcodeScannerErrorOccurredEventData structure](ns-pointofservicedriverinterface-_posbarcodescannererroroccurredeventdata.md) | This structure contains the error data that is passed to the BarcodeScannerErrorOccurred event. |
| [_PosDeviceBasicsType structure](ns-pointofservicedriverinterface-_posdevicebasicstype.md) | This structure indicates the type of device, version, and recommended buffer size as specified by the driver. |
| [_PosEventDataHeader structure](ns-pointofservicedriverinterface-_poseventdataheader.md) | This structure describes the scanned image data that is passed to the BarcodeScannerImagePreviewReceived event. |
| [_PosMagneticStripeReaderCapabilitiesType structure](ns-pointofservicedriverinterface-_posmagneticstripereadercapabilitiestype.md) | This structure defines the kinds of magnetic stripe reader (MSR) capabilities that a device supports, such as whether the device supports track data masking. |
| [_PosProfileType structure](ns-pointofservicedriverinterface-_posprofiletype.md) | This structure describes the number of profile strings in a buffer. |
| [_PosStatisticsHeader structure](ns-pointofservicedriverinterface-_posstatisticsheader.md) | This structure defines Unified Point of Service (UPOS) standard information about a device. This structure is the header for an incoming statistic. |
| [_PosStatusUpdatedEventData structure](ns-pointofservicedriverinterface-_posstatusupdatedeventdata.md) | This structure contains data passed to the StatusUpdated event. |
| [_PosStringType structure](ns-pointofservicedriverinterface-_posstringtype.md) | This structure represents a Point of Service (POS) unicode string with a length of DataLengthInBytes. |
| [_PosValueStatisticsEntry structure](ns-pointofservicedriverinterface-_posvaluestatisticsentry.md) | This structure contains the value of a statistic. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_POINT_OF_SERVICE_CHECK_HEALTH IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_check_health.md) | This I/O control function checks the device health. |
| [IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device.md) | The I/O control function claims the device for exclusive access. |
| [IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_get_device_basics.md) | This I/O control function gets the type of device, version, and recommended buffer size as specified by the driver. |
| [IOCTL_POINT_OF_SERVICE_GET_PROPERTY IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_get_property.md) | This I/O control function returns the value of the specified property from the device driver. |
| [IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_msr_authenticate_device.md) | This IO control function authenticates the magnetic stripe reader (MSR). |
| [IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_msr_deauthenticate_device.md) | This I/O control function deauthenticates the magnetic stripe reader (MSR). |
| [IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_msr_retrieve_device_authentication.md) | This I/O control function retrieves the device authentication type. |
| [IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_msr_update_key.md) | This I/O control function sets a new encryption key. |
| [IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_release_device.md) | This I/O control function is called when a client is ready to relinquish its claim on a device. |
| [IOCTL_POINT_OF_SERVICE_RESET_STATISTICS IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_reset_statistics.md) | This I/O control function resets the specified statistic's value to zero. |
| [IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_retain_device.md) | This I/O control function is used to keep a claim on a device when a client is notified that its claim on the device is being contested by another client. |
| [IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics.md) | This I/O control function returns unified point of service (UPOS) standard information about a device such as its category, manufacturer, and firmware revision number. |
| [IOCTL_POINT_OF_SERVICE_SET_PROPERTY IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_set_property.md) | This I/O control function sets the specified property on the device. |
| [IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS IOCTL](ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics.md) | This I/O control function sets the specified statistic to the value in the input buffer. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_MsrAuthenticationProtocol enumeration](ne-pointofservicedriverinterface-_msrauthenticationprotocol.md) | This enumeration defines magnetic stripe reader (MSR) authentication protocols. |
| [_MsrCardType enumeration](ne-pointofservicedriverinterface-_msrcardtype.md) | This enumeration defines the kinds of magnetic stripe cards. |
| [_MsrDataEncryption enumeration](ne-pointofservicedriverinterface-_msrdataencryption.md) | This enumeration defines the kind of encryption algorithm supported by the magnetic stripe reader (MSR). |
| [_MsrErrorReportingType enumeration](ne-pointofservicedriverinterface-_msrerrorreportingtype.md) | This enumeration defines the constants that indicate the error reporting type for the magnetic stripe reader (MSR). |
| [_MsrStatisticsEntryType enumeration](ne-pointofservicedriverinterface-_msrstatisticsentrytype.md) | This enumeration defines the kinds of magnetic stripe reader statistics. |
| [_MsrStatusUpdateType enumeration](ne-pointofservicedriverinterface-_msrstatusupdatetype.md) | This enumeration defines the constants that indicate the magnetic stripe reader (MSR) status. |
| [_MsrTrackErrorType enumeration](ne-pointofservicedriverinterface-_msrtrackerrortype.md) | This enumeration defines the kinds of magnetic stripe reader track errors. |
| [_MsrTrackIds enumeration](ne-pointofservicedriverinterface-_msrtrackids.md) | Defines the constants that represent the magnetic stripe reader (MSR) tracks. |
| [_PosDeviceControlType enumeration](ne-pointofservicedriverinterface-_posdevicecontroltype.md) | This enumeration defines values for the IOCTLs of the scanner driver and magnetic stripe reader (MSR) driver. |
| [_PosEventType enumeration](ne-pointofservicedriverinterface-_poseventtype.md) | This enumeration defines values used in the PosEventDataHeader structure to indicate the type of event that was raised. |
| [_PosPropertyId enumeration](ne-pointofservicedriverinterface-_pospropertyid.md) | This enumeration defines the property identifiers for the properties that device drivers need to handle to be considered a barcode scanner or a magnetic strip reader (MSR). |
