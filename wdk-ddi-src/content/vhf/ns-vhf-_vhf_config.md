---
UID: NS:vhf._VHF_CONFIG
title: "_VHF_CONFIG"
author: windows-driver-content
description: Contains initial configuration information that is provided by the HID source driver when it calls VhfCreate to create a virtual HID device.
old-location: hid\vhf_config.htm
old-project: hid
ms.assetid: 384BE20B-0F40-418D-B24E-9711BF7CE53A
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PVHF_CONFIG, PVHF_CONFIG, PVHF_CONFIG structure pointer [Human Input Devices], VHF_CONFIG, VHF_CONFIG structure [Human Input Devices], _VHF_CONFIG, hid.vhf_config, vhf/PVHF_CONFIG, vhf/VHF_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: vhf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	vhf.h
api_name:
-	VHF_CONFIG
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# _VHF_CONFIG structure


## -description


Contains initial configuration information that is provided by the HID source driver when it calls <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a> to create a virtual HID device.


## -syntax


````
typedef struct _VHF_CONFIG {
  ULONG                                            Size;
  PVOID                                            VhfClientContext;
  ULONG                                            OperationContextSize;
  PDEVICE_OBJECT                                   DeviceObject;
  USHORT                                           VendorID;
  USHORT                                           ProductID;
  USHORT                                           VersionNumber;
  GUID                                             ContainerID;
  USHORT                                           ReportDescriptorLength;
  _Field_size_full_(ReportDescriptorLength) PUCHAR ReportDescriptor;
  PEVT_VHF_READY_FOR_NEXT_READ_REPORT              EvtVhfReadyForNextReadReport;
  PEVT_VHF_ASYNC_OPERATION                         EvtVhfAsyncOperationGetFeature;
  PEVT_VHF_ASYNC_OPERATION                         EvtVhfAsyncOperationSetFeature;
  PEVT_VHF_ASYNC_OPERATION                         EvtVhfAsyncOperationWriteReport;
  PEVT_VHF_ASYNC_OPERATION                         EvtVhfAsyncOperationGetInputReport;
  PEVT_VHF_CLEANUP                                 EvtVhfCleanup;
} VHF_CONFIG, *PVHF_CONFIG;
````


## -struct-fields




### -field Size

Required. Size of this structure initialized by <a href="..\vhf\nf-vhf-vhf_config_init.md">VHF_CONFIG_INIT</a>.


### -field VhfClientContext

Optional. An opaque pointer to HID source driver-allocated memory that the Virtual HID Framework (VHF) passes when it invokes  those callback functions.


### -field OperationContextSize

Optional. Size of the buffer that VHF must allocate for an asynchronous operation started by <a href="..\vhf\nc-vhf-evt_vhf_async_operation.md">EvtVhfAsyncOperation</a>. If non-zero, VHF allocates a buffer of this size and passes a pointer to that buffer in the <i>VhfOperationContext</i> parameter each time it invokes <i>EvtVhfAsyncOperation</i> to start a new operation.


### -field DeviceObject

Required. A pointer to the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure for the HID source driver. Get that pointer by calling  <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmgetdeviceobject.md">WdfDeviceWdmGetDeviceObject</a> and passing the WDFDEVICE handle that the driver received in the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> call. 


### -field Reserved

 


### -field VendorID

Optional. Vendor ID of the virtual HID device to be created.


### -field ProductID

Optional. Product ID of the virtual HID device to be created.


### -field VersionNumber

Optional. Version number of the virtual HID device to be created.


### -field ContainerID

Optional. Container ID of the virtual HID device to be created.


### -field InstanceIDLength

 


### -field InstanceID

 


### -field ReportDescriptorLength

Required. The length of the HID Report Descriptor contained in a buffer pointed by <b>ReportDescriptor</b>.


### -field ReportDescriptor

Required. A pointer to a HID source driver-allocated buffer that contains the  HID Report Descriptor.


### -field EvtVhfReadyForNextReadReport

Optional. A pointer to an <a href="..\vhf\nc-vhf-evt_vhf_ready_for_next_read_report.md">EvtVhfReadyForNextReadReport</a> callback. The HID source driver must implement and register this callback function if it wants to handle the buffering policy for submitting HID Input Reports. If this callback is specified, VHF does not buffer those reports. The HID source driver should submit one report by calling <a href="..\vhf\nf-vhf-vhfreadreportsubmit.md">VhfReadReportSubmit</a>, each time VHF invokes   <i>EvtVhfReadyForNextReadReport</i>.


### -field EvtVhfAsyncOperationGetFeature

Optional. A pointer to an <a href="..\vhf\nc-vhf-evt_vhf_async_operation.md">EvtVhfAsyncOperation</a> callback. The HID source driver must implement and register this callback function if it wants to a get a HID Feature Report associated with a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">Top-Level Collection</a> from the HID class driver pair.
The driver can get a Feature Report only if the Report Descriptor declares it.


### -field EvtVhfAsyncOperationSetFeature

Optional. A pointer to an <a href="..\vhf\nc-vhf-evt_vhf_async_operation.md">EvtVhfAsyncOperation</a> callback. The HID source driver must implement and register this callback function if it wants to a send  a HID Feature Report associated with a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">Top-Level Collection</a> to the HID class driver pair. The driver can set a Feature Report only if the Report Descriptor declares it.


### -field EvtVhfAsyncOperationWriteReport

Optional. A pointer to an <a href="..\vhf\nc-vhf-evt_vhf_async_operation.md">EvtVhfAsyncOperation</a> callback. The HID source driver must implement and register this callback function if it wants to a support HID Output Reports and send  them to the  HID class driver pair. 


### -field EvtVhfAsyncOperationGetInputReport

Optional. A pointer to an <a href="..\vhf\nc-vhf-evt_vhf_async_operation.md">EvtVhfAsyncOperation</a> callback. The HID source driver must implement and register this callback function if it wants to support on-demand query for Input Reports.


### -field EvtVhfCleanup

Optional. A pointer to a <a href="..\vhf\nc-vhf-evt_vhf_cleanup.md">EvtVhfCleanup</a> callback. The HID source driver can implement and register this callback function if it wants to free the allocated resources for the virtual HID device. 


### -field HardwareIDsLength

 


### -field HardwareIDs

 




## -see-also

<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20VHF_CONFIG structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

