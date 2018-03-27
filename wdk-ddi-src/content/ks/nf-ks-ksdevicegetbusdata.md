---
UID: NF:ks.KsDeviceGetBusData
title: KsDeviceGetBusData function
author: windows-driver-content
description: The KsDeviceGetBusData function reads data from the bus where the given AVStream device resides.
old-location: stream\ksdevicegetbusdata.htm
old-project: stream
ms.assetid: 40971ff3-6fd3-480b-aba9-7f572d6e1ce2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsDeviceGetBusData, KsDeviceGetBusData function [Streaming Media Devices], avfunc_3106cd50-9e8c-407c-bcb0-c5e9c86d8dc7.xml, ks/KsDeviceGetBusData, stream.ksdevicegetbusdata
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
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsDeviceGetBusData
product: Windows
targetos: Windows
req.typenames: 
---

# KsDeviceGetBusData function


## -description


The<b> KsDeviceGetBusData</b> function reads data from the bus where the given AVStream device resides.


## -parameters




### -param Device [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure representing the given AVStream device for which data from the bus should be read. 


### -param DataType [in]

This parameter indicates the type of bus data to be read. Zero corresponds to configuration space. For further information, see the discussion of <b>WhichSpace</b> in the reference page for <a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>.


### -param Buffer [in]

A pointer to a buffer that receives the data read from the bus. Must be at least as large as <i>Length</i>.


### -param Offset [in]

This parameter contains the byte offset in the space specified by <i>DataType</i> from which data is read.


### -param Length [in]

This parameter specifies the number of bytes to read into <i>Buffer</i>.


## -returns



<b>KsDeviceGetBusData </b>returns the number of bytes actually read from the bus. If an errors occurs, this value is zero.




## -remarks



Depending on the driver for the bus where the specified device resides, there are two possible behaviors and restriction sets on this function. If the given bus driver supports the bus interface standard (usually PCI), call this function at either IRQL = PASSIVE_LEVEL or DISPATCH_LEVEL. After such a call, <b>KsDeviceGetBusData</b> returns the actual number of bytes read from the requested space. If, however, the given bus driver does not support the bus interface standard, then AVStream communicates with the bus driver through <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>. Note that this restricts use of <b>KsDeviceGetBusData</b> to IRQL = PASSIVE_LEVEL and also means that the return value is either 0, in the case of failure, or equal to<i> Length</i> if data acquisition was successful<i>.</i>

To ensure compatibility, minidriver writers may want to restrict use of <b>KsDeviceGetBusData</b> to IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561690">KsDeviceSetBusData</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeviceGetBusData function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

