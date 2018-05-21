---
UID: TP:pos
ms.assetid: 01ba4b30-aac9-383a-b7a2-32c112dfd250
ms.author: windowsdriverdev
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Point of Service (POS)

## -description

Overview of the Point of Service (POS) technology.

To develop Point of Service (POS), you need these headers:

 * [pointofservicecommontypes.h](..\pointofservicecommontypes\index.md)
 * [pointofservicedriverinterface.h](..\pointofservicedriverinterface\index.md)
 * [poscx.h](..\poscx\index.md)
 * [poscxfuncenum.h](..\poscxfuncenum\index.md)

For the programming guide, see [Point of Service (POS)](https://docs.microsoft.com/en-us/windows-hardware/drivers/pos).

## Functions

| Title   | Description   |
| ---- |:---- |
| [POS_CX_ATTRIBUTES_INIT function](..\poscx\nf-poscx-pos_cx_attributes_init.md) | POS_CX_ATTRIBUTES_INIT initializes a POS_CX_ATTRIBUTE structure. |
| [PosCxClaimDevice function](..\poscx\nf-poscx-poscxclaimdevice.md) | PosCxClaimDevice is called to claim a device for exclusive use. The caller should call PosCxReleaseDevice when the device is no longer needed. |
| [PosCxCleanPendingRequests function](..\poscx\nf-poscx-poscxcleanpendingrequests.md) | PosCxCleanPendingRequests is called to cancel all pending requests for a given caller, identified by the open instance. |
| [PosCxCleanupEvents function](..\poscx\nf-poscx-poscxcleanupevents.md) | PosCxCleanupEvents is called to clean up all pending events for a given caller, identified by the open instance. |
| [PosCxClose function](..\poscx\nf-poscx-poscxclose.md) | PosCxClose is called to delete an opened PosCx library instance. This function releases the device if the caller is the owner, and cancels pending requests. It should be called from the driver's EVT_WDF_FILE_CLOSE callback. |
| [PosCxGetDeviceInterfaceTag function](..\poscx\nf-poscx-poscxgetdeviceinterfacetag.md) | PosCxGetDeviceInterfaceTag returns the device interface tag that is set in PosCxOpen. |
| [PosCxGetPendingEvent function](..\poscx\nf-poscx-poscxgetpendingevent.md) | PosCxGetPendingEvent is called either from the device read callback, or when a new event arrives. |
| [PosCxInit function](..\poscx\nf-poscx-poscxinit.md) | PosCxInit is called to initialize the PosCx library's internal resources. The resources are tied to the device, and are released when the device goes away. |
| [PosCxIsDeviceOwner function](..\poscx\nf-poscx-poscxisdeviceowner.md) | PosCxIsDeviceOwner checks if the caller currently owns the claim on the device. |
| [PosCxIsPosApp function](..\poscx\nf-poscx-poscxisposapp.md) | PosCxIsPosApp checks if the open instance is associated with a point-of-service application. |
| [PosCxMarkPosApp function](..\poscx\nf-poscx-poscxmarkposapp.md) | PosCxMarkPosApp marks the open instance as associated or not associated with a point-of-service application. |
| [PosCxOpen function](..\poscx\nf-poscx-poscxopen.md) | PosCxOpen is called to create an open PosCx library instance. This function initializes all resources it needs to manage a single open instance. It should be called from the driver's EVT_WDF_DEVICE_FILE_CREATE callback. |
| [PosCxPutPendingEvent function](..\poscx\nf-poscx-poscxputpendingevent.md) | PosCxPutPendingEvent creates a new event object, copies the event data to the new event object, and tries to delegate it to the waiting caller. |
| [PosCxPutPendingEventMemory function](..\poscx\nf-poscx-poscxputpendingeventmemory.md) | PosCxPutPendingEventMemory tries to delegate a memory object containing the event data to a waiting caller. If the target caller does not have a read request waiting, the new event is added to the designated event queue (control or data). |
| [PosCxReleaseDevice function](..\poscx\nf-poscx-poscxreleasedevice.md) | PosCxReleaseDevice is called to release a device that was previously claimed with PosCxClaimDevice. Once the device is released, the next pending claim requester is promoted. |
| [PosCxRemoteRequestRelease function](..\poscx\nf-poscx-poscxremoterequestrelease.md) | PosCxRemoteRequestRelease is called whenever a remote device asks for the device to release. This initiates claim negotiation. |
| [PosCxRetainDevice function](..\poscx\nf-poscx-poscxretaindevice.md) | PosCxRetainDevice is called to extend the ownership of the device. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback function](..\poscx\nc-poscx-evt_pos_cx_device_ownership_change.md) | The EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback is called during the API claim ownership transition. The driver is expected to set the device back to a default state in this routine. |
| [EVT_POS_CX_DEVICE_REMOTE_CLAIM callback function](..\poscx\nc-poscx-evt_pos_cx_device_remote_claim.md) | The EVT_POS_CX_DEVICE_REMOTE_CLAIM callback is called when the device is transitioning from unclaimed to claimed and allows the driver to do additional work. |
| [EVT_POS_CX_DEVICE_REMOTE_RELEASE callback function](..\poscx\nc-poscx-evt_pos_cx_device_remote_release.md) | The EVT_POS_CX_DEVICE_REMOTE_RELEASE callback is called whenever the device is released and left with no owner and allows the driver to do additional work. |
| [EVT_POS_CX_DEVICE_REMOTE_RETAIN callback function](..\poscx\nc-poscx-evt_pos_cx_device_remote_retain.md) | The EVT_POS_CX_DEVICE_REMOTE_RETAIN callback is called whenever PosCx attempts to hold onto a claim on a network device and allows the driver to do additional work. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_BarcodeSymbologyAttributesData structure](..\pointofservicecommontypes\ns-pointofservicecommontypes-_barcodesymbologyattributesdata.md) | The BarcodeSymbologyAttributesData structure contains the attribute information for a barcode symbology. |
| [_LineDisplayCharacterData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_linedisplaycharacterdata.md) | This structure is not implemented. |
| [_LineDisplayCursorCoordinates structure](..\pointofservicecommontypes\ns-pointofservicecommontypes-_linedisplaycursorcoordinates.md) | This structure is not implemented. |
| [_LineDisplayGlyphDefinitionData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_linedisplayglyphdefinitiondata.md) | This structure is not implemented. |
| [_LineDisplaySetBitmapData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_linedisplaysetbitmapdata.md) | This structure is not implemented. |
| [_LineDisplaySetDescriptorData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_linedisplaysetdescriptordata.md) | This structure is not implemented. |
| [_LineDisplaySizeInPixelsType structure](..\pointofservicecommontypes\ns-pointofservicecommontypes-_linedisplaysizeinpixelstype.md) | This structure is not implemented. |
| [_LineDisplayWindowDisplayBitmapData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_linedisplaywindowdisplaybitmapdata.md) | This structure is not implemented. |
| [_MSR_AUTHENTICATE_DEVICE structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_authenticate_device.md) | This structure provides the authentication information used to authenticate a device. |
| [_MSR_DATA_RECEIVED structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_data_received.md) | This structure contains the data read from a swiped magnetic stripe card. |
| [_MSR_DEAUTHENTICATE_DEVICE structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_deauthenticate_device.md) | This structure provides the information necessary to deauthenticate the device. |
| [_MSR_ERROR_EVENT structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_error_event.md) | This structure contains the error data that is passed to the MagneticStripeReaderErrorOccured event. |
| [_MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_retrieve_device_authentication_data.md) | This structure contains authentication information retrieved from the device. |
| [_MSR_SUPPORTED_CARD_TYPES structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_supported_card_types.md) | This structure defines the types of magnetic stripe cards supported by the reader. |
| [_MSR_UPDATE_KEY structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_update_key.md) | This structure contains the information necessary to set a new encryption key. |
| [_POS_CX_ATTRIBUTES structure](..\poscx\ns-poscx-_pos_cx_attributes.md) | The POS_CX_ATTRIBUTES structure contains pointers to event callback functions implemented by the client driver. |
| [_PosBarcodeScanDataTypeData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posbarcodescandatatypedata.md) | This structure describes a buffer of barcode symbologies supported by the driver. |
| [_PosBarcodeScannerCapabilitiesType structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posbarcodescannercapabilitiestype.md) | This structure defines the type of scanner capabilities that a device supports such as whether the device supports statistics reporting and image preview. |
| [_PosBarcodeScannerDataReceivedEventData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posbarcodescannerdatareceivedeventdata.md) | This structure contains the scanned data that is passed to the BarcodeScannerDataReceived event. |
| [_PosBarcodeScannerErrorOccurredEventData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posbarcodescannererroroccurredeventdata.md) | This structure contains the error data that is passed to the BarcodeScannerErrorOccurred event. |
| [_PosDeviceBasicsType structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posdevicebasicstype.md) | This structure indicates the type of device, version, and recommended buffer size as specified by the driver. |
| [_PosDeviceInformation structure](..\pointofservicecommontypes\ns-pointofservicecommontypes-_posdeviceinformation.md) | This structure provides device information as defined in and required by the Unified Point of Service (UPOS) standard. |
| [_PosEventDataHeader structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_poseventdataheader.md) | This structure describes the scanned image data that is passed to the BarcodeScannerImagePreviewReceived event. |
| [_PosMagneticStripeReaderCapabilitiesType structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posmagneticstripereadercapabilitiestype.md) | This structure defines the kinds of magnetic stripe reader (MSR) capabilities that a device supports, such as whether the device supports track data masking. |
| [_PosProfileType structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posprofiletype.md) | This structure describes the number of profile strings in a buffer. |
| [_PosStatisticsHeader structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posstatisticsheader.md) | This structure defines Unified Point of Service (UPOS) standard information about a device. This structure is the header for an incoming statistic. |
| [_PosStatusUpdatedEventData structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posstatusupdatedeventdata.md) | This structure contains data passed to the StatusUpdated event. |
| [_PosStringType structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posstringtype.md) | This structure represents a Point of Service (POS) unicode string with a length of DataLengthInBytes. |
| [_PosValueStatisticsEntry structure](..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posvaluestatisticsentry.md) | This structure contains the value of a statistic. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [DriverMagneticStripeReaderAuthenticationLevel enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-drivermagneticstripereaderauthenticationlevel.md) | This enumeration defines the levels of magnetic stripe reader (MSR) authentication support. |
| [DriverUnifiedPosErrorReason enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedposerrorreason.md) | This enumeration indicates the reason for the error. |
| [DriverUnifiedPosErrorSeverity enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedposerrorseverity.md) | This enumeration indicates the severity of the error. |
| [DriverUnifiedPosHealthCheckLevel enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedposhealthchecklevel.md) | This enumeration indicates the type of health check to be performed when CheckHealthAsync is called on a POS device. |
| [DriverUnifiedPosPowerReportingType enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedpospowerreportingtype.md) | This enumeration defines the type of power reporting that is supported by the device (for example, advanced, standard, and so on). |
| [DriverUnifiedPosPowerState enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-driverunifiedpospowerstate.md) | This enumeration is not implemented. |
| [LineDisplayBitmapWidth enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-linedisplaybitmapwidth.md) | This enumeration is not implemented. |
| [LineDisplayCursorCapabilities enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-linedisplaycursorcapabilities.md) | This enumeration is not implemented. |
| [LineDisplayCursorTypeFlags enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-linedisplaycursortypeflags.md) | This enumeration is not implemented. |
| [LineDisplayHorizontalBitmapAlignment enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-linedisplayhorizontalbitmapalignment.md) | This enumeration is not implemented. |
| [LineDisplayVerticalBitmapAlignment enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-linedisplayverticalbitmapalignment.md) | This enumeration is not implemented. |
| [_BarcodeStatus enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-_barcodestatus.md) | This enumeration indicates barcode scanner status values. |
| [_BarcodeSymbology enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-_barcodesymbology.md) | This enumeration defines the barcode symbologies. |
| [_BarcodeSymbologyDecodeLengthType enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-_barcodesymbologydecodelengthtype.md) | The BarcodeSymbologyDecodeLengthType enum describes values for the decode length which can be set to support a range, two discrete values, or be set to any length. |
| [_LineDisplayMarqueeFormatType enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-_linedisplaymarqueeformattype.md) | This enumeration is not implemented. |
| [_LineDisplayMarqueeTypeType enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-_linedisplaymarqueetypetype.md) | This enumeration is not implemented. |
| [_LineDisplayStatusType enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-_linedisplaystatustype.md) | This enumeration is not implemented. |
| [_MsrAuthenticationProtocol enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrauthenticationprotocol.md) | This enumeration defines magnetic stripe reader (MSR) authentication protocols. |
| [_MsrCardType enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrcardtype.md) | This enumeration defines the kinds of magnetic stripe cards. |
| [_MsrDataEncryption enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrdataencryption.md) | This enumeration defines the kind of encryption algorithm supported by the magnetic stripe reader (MSR). |
| [_MsrErrorReportingType enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrerrorreportingtype.md) | This enumeration defines the constants that indicate the error reporting type for the magnetic stripe reader (MSR). |
| [_MsrStatisticsEntryType enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrstatisticsentrytype.md) | This enumeration defines the kinds of magnetic stripe reader statistics. |
| [_MsrStatusUpdateType enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrstatusupdatetype.md) | This enumeration defines the constants that indicate the magnetic stripe reader (MSR) status. |
| [_MsrTrackErrorType enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrtrackerrortype.md) | This enumeration defines the kinds of magnetic stripe reader track errors. |
| [_MsrTrackIds enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_msrtrackids.md) | Defines the constants that represent the magnetic stripe reader (MSR) tracks. |
| [_POS_CX_EVENT_ATTRIBUTES enumeration](..\poscx\ne-poscx-_pos_cx_event_attributes.md) | The POS_CX_EVENT_ATTRIBUTES describes the priority and access rights for the POS events coming from the device. The values are a combination of the values defined in POS_CX_EVENT_DEST and POS_CX_EVENT_PRIORITY. |
| [_POS_CX_EVENT_DEST enumeration](..\poscx\ne-poscx-_pos_cx_event_dest.md) | The POS_CX_EVENT_DEST defines which applications receive this event. |
| [_POS_CX_EVENT_PRIORITY enumeration](..\poscx\ne-poscx-_pos_cx_event_priority.md) | The POS_CX_EVENT_PRIORITY defines the importance of the event and the order it will be delivered to the client application. |
| [_PosDeviceControlType enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_posdevicecontroltype.md) | This enumeration defines values for the IOCTLs of the scanner driver and magnetic stripe reader (MSR) driver. |
| [_PosDeviceType enumeration](..\pointofservicecommontypes\ne-pointofservicecommontypes-_posdevicetype.md) | This enumeration defines values used in the PosDeviceBasicsType structure to indicate the type of device (for instance, barcode scanner or magnetic stripe reader). |
| [_PosEventType enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_poseventtype.md) | This enumeration defines values used in the PosEventDataHeader structure to indicate the type of event that was raised. |
| [_PosPropertyId enumeration](..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_pospropertyid.md) | This enumeration defines the property identifiers for the properties that device drivers need to handle to be considered a barcode scanner or a magnetic strip reader (MSR). |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_POINT_OF_SERVICE_CHECK_HEALTH IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_check_health.md) | This I/O control function checks the device health. |
| [IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device.md) | The I/O control function claims the device for exclusive access. |
| [IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_get_device_basics.md) | This I/O control function gets the type of device, version, and recommended buffer size as specified by the driver. |
| [IOCTL_POINT_OF_SERVICE_GET_PROPERTY IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_get_property.md) | This I/O control function returns the value of the specified property from the device driver. |
| [IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_authenticate_device.md) | This IO control function authenticates the magnetic stripe reader (MSR). |
| [IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_deauthenticate_device.md) | This I/O control function deauthenticates the magnetic stripe reader (MSR). |
| [IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_retrieve_device_authentication.md) | This I/O control function retrieves the device authentication type. |
| [IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_msr_update_key.md) | This I/O control function sets a new encryption key. |
| [IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_release_device.md) | This I/O control function is called when a client is ready to relinquish its claim on a device. |
| [IOCTL_POINT_OF_SERVICE_RESET_STATISTICS IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_reset_statistics.md) | This I/O control function resets the specified statistic's value to zero. |
| [IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_retain_device.md) | This I/O control function is used to keep a claim on a device when a client is notified that its claim on the device is being contested by another client. |
| [IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics.md) | This I/O control function returns unified point of service (UPOS) standard information about a device such as its category, manufacturer, and firmware revision number. |
| [IOCTL_POINT_OF_SERVICE_SET_PROPERTY IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_set_property.md) | This I/O control function sets the specified property on the device. |
| [IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS IOCTL](..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics.md) | This I/O control function sets the specified statistic to the value in the input buffer. |
