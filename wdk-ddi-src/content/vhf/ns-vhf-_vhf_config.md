---
UID: NS:vhf._VHF_CONFIG
title: _VHF_CONFIG (vhf.h)
description: Contains initial configuration information that is provided by the HID source driver when it calls VhfCreate to create a virtual HID device.
old-location: hid\vhf_config.htm
tech.root: hid
ms.assetid: 384BE20B-0F40-418D-B24E-9711BF7CE53A
ms.date: 04/30/2018
ms.keywords: "*PVHF_CONFIG, PVHF_CONFIG, PVHF_CONFIG structure pointer [Human Input Devices], VHF_CONFIG, VHF_CONFIG structure [Human Input Devices], _VHF_CONFIG, hid.vhf_config, vhf/PVHF_CONFIG, vhf/VHF_CONFIG"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- vhf.h
api_name:
- VHF_CONFIG
product:
- Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
---

# _VHF_CONFIG structure


## -description


Contains initial configuration information that is provided by the HID source driver when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/dn925036">VhfCreate</a> to create a virtual HID device.


## -struct-fields




### -field Size

Required. Size of this structure initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/dn925046">VHF_CONFIG_INIT</a>.


### -field VhfClientContext

Optional. An opaque pointer to HID source driver-allocated memory that the Virtual HID Framework (VHF) passes when it invokes  those callback functions.


### -field OperationContextSize

Optional. Size of the buffer that VHF must allocate for an asynchronous operation started by <a href="https://msdn.microsoft.com/C42174FE-202F-405D-840B-8613762F43AC">EvtVhfAsyncOperation</a>. If non-zero, VHF allocates a buffer of this size and passes a pointer to that buffer in the <i>VhfOperationContext</i> parameter each time it invokes <i>EvtVhfAsyncOperation</i> to start a new operation.


### -field DeviceObject

Required. A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure for the HID source driver. Get that pointer by calling  <a href="https://msdn.microsoft.com/library/windows/hardware/ff546942">WdfDeviceWdmGetDeviceObject</a> and passing the WDFDEVICE handle that the driver received in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> call. 


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

Optional. A pointer to an <a href="https://msdn.microsoft.com/02DDBE00-C342-474B-8D06-FBB929BA4760">EvtVhfReadyForNextReadReport</a> callback. The HID source driver must implement and register this callback function if it wants to handle the buffering policy for submitting HID Input Reports. If this callback is specified, VHF does not buffer those reports. The HID source driver should submit one report by calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn925040">VhfReadReportSubmit</a>, each time VHF invokes   <i>EvtVhfReadyForNextReadReport</i>.


### -field EvtVhfAsyncOperationGetFeature

Optional. A pointer to an <a href="https://msdn.microsoft.com/C42174FE-202F-405D-840B-8613762F43AC">EvtVhfAsyncOperation</a> callback. The HID source driver must implement and register this callback function if it wants to a get a HID Feature Report associated with a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">Top-Level Collection</a> from the HID class driver pair.
The driver can get a Feature Report only if the Report Descriptor declares it.


### -field EvtVhfAsyncOperationSetFeature

Optional. A pointer to an <a href="https://msdn.microsoft.com/C42174FE-202F-405D-840B-8613762F43AC">EvtVhfAsyncOperation</a> callback. The HID source driver must implement and register this callback function if it wants to a send  a HID Feature Report associated with a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">Top-Level Collection</a> to the HID class driver pair. The driver can set a Feature Report only if the Report Descriptor declares it.


### -field EvtVhfAsyncOperationWriteReport

Optional. A pointer to an <a href="https://msdn.microsoft.com/C42174FE-202F-405D-840B-8613762F43AC">EvtVhfAsyncOperation</a> callback. The HID source driver must implement and register this callback function if it wants to a support HID Output Reports and send  them to the  HID class driver pair. 


### -field EvtVhfAsyncOperationGetInputReport

Optional. A pointer to an <a href="https://msdn.microsoft.com/C42174FE-202F-405D-840B-8613762F43AC">EvtVhfAsyncOperation</a> callback. The HID source driver must implement and register this callback function if it wants to support on-demand query for Input Reports.


### -field EvtVhfCleanup

Optional. A pointer to a <a href="https://msdn.microsoft.com/1D477E7B-E4EA-46E7-872C-3BEBFBD31702">EvtVhfCleanup</a> callback. The HID source driver can implement and register this callback function if it wants to free the allocated resources for the virtual HID device. 


### -field HardwareIDsLength

 


### -field HardwareIDs

 




## -see-also




<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
 

 

