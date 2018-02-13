---
UID: NF:ks.KsDeviceSetBusData
title: KsDeviceSetBusData function
author: windows-driver-content
description: The KsDeviceSetBusData function writes data to the bus on which the specified AVStream device resides.
old-location: stream\ksdevicesetbusdata.htm
old-project: stream
ms.assetid: b319f2a4-dbbe-4324-8f8d-a42bb40d7939
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsDeviceSetBusData, stream.ksdevicesetbusdata, ks/KsDeviceSetBusData, avfunc_5b7ad4e8-d651-4b80-99db-260fba83ce15.xml, KsDeviceSetBusData function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsDeviceSetBusData
product: Windows
targetos: Windows
req.typenames: 
---

# KsDeviceSetBusData function


## -description


The<b> KsDeviceSetBusData </b>function writes data to the bus on which the specified AVStream device resides.


## -syntax


````
ULONG KsDeviceSetBusData(
  _In_ PKSDEVICE Device,
  _In_ ULONG     DataType,
  _In_ PVOID     Buffer,
  _In_ ULONG     Offset,
  _In_ ULONG     Length
);
````


## -parameters




### -param Device [in]

A pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure. This routine attempts to write data to the bus on which this device resides.


### -param DataType [in]

This parameter indicates the type of bus data to be written. Zero corresponds to configuration space. For further information, see the discussion of <b>WhichSpace</b> in the reference page for <a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>.


### -param Buffer [in]

A pointer to a buffer that contains the data to write to the bus. Number of bytes in the buffer must be equal or greater than <i>Length</i>.


### -param Offset [in]

This parameter contains the byte offset into the space specified by <i>DataType</i> where data is written.


### -param Length [in]

This parameter specifies the number of bytes of data to write to the bus from <i>Buffer.</i>


## -returns



<b>KsDeviceSetBusData</b> returns the number of bytes actually written to the bus. In the case of an error, the routine returns zero. See details below in the Remarks section.




## -remarks



This function performs differently depending on the driver for the bus on which the specified device resides. If the bus driver supports the bus interface standard (usually PCI), call this function at either IRQL = PASSIVE_LEVEL or DISPATCH_LEVEL. After such a call, <b>KsDeviceSetBusData</b> returns the actual number of bytes written to the requested space.

If the bus driver does not support the bus interface standard, AVStream communicates with the bus driver using <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>. In this case, call <b>KsDeviceSetBusData</b> at IRQL = PASSIVE_LEVEL. The return value is either zero, in the case of failure, or equal to <i>Length</i> if the data was written successfully.

Drivers running on Windows 2000 and later can make this call at IRQL = DISPATCH_LEVEL. However, to ensure compatibility, minidriver writers may want to restrict use of <b>KsDeviceSetBusData</b> to IRQL = PASSIVE_LEVEL.




## -see-also

<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>



<a href="..\ks\nf-ks-ksdevicegetbusdata.md">KsDeviceGetBusData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeviceSetBusData function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

