---
UID: NF:wdm.IoGetDeviceInterfacePropertyData
title: IoGetDeviceInterfacePropertyData function
author: windows-driver-content
description: The IoGetDeviceInterfacePropertyData routine retrieves the current value of a device interface property.
old-location: kernel\iogetdeviceinterfacepropertydata.htm
old-project: kernel
ms.assetid: 01113C73-2C79-40F2-9B13-B864148D2C9A
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoGetDeviceInterfacePropertyData, IoGetDeviceInterfacePropertyData routine [Kernel-Mode Driver Architecture], kernel.iogetdeviceinterfacepropertydata, wdm/IoGetDeviceInterfacePropertyData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetDeviceInterfacePropertyData
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetDeviceInterfacePropertyData function


## -description


The <b>IoGetDeviceInterfacePropertyData</b> routine retrieves the current value of a <a href="https://msdn.microsoft.com/43aa0ce6-a06b-43e4-a213-300554391ae0">device interface property</a>.


## -parameters




### -param SymbolicLinkName [in]

A pointer to a string that identifies the device interface instance. This string was obtained from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549186">IoGetDeviceInterfaces</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549180">IoGetDeviceInterfaceAlias</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549506">IoRegisterDeviceInterface</a> routine.


### -param PropertyKey [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> structure that contains the device interface property key.


### -param Lcid [in]

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>. The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>. For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/en-us/library/cc233968(PROT.10).aspx">LCID Structure</a>.


### -param Flags

Reserved for system use. Drivers should set this value to zero.


### -param Size [in]

Specifies the size, in bytes, of the buffer that <i>Data</i> points to.


### -param Data [out]

A pointer to a caller-allocated buffer into which the routine writes the device interface property data.


### -param RequiredSize [out]

A pointer to a ULONG variable into which <b>IoGetDeviceInterfacePropertyData</b> writes the required size of the property data.  If the routine succeeds, the required size value is the number of bytes that the routine writes to the output buffer that <i>Data</i> points to. If the routine returns STATUS_BUFFER_TOO_SMALL, the required size value is the size of the buffer that the caller should allocate for this property value.


### -param Type [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543546">DEVPROPTYPE</a> variable. If <b>IoGetDeviceInterfacePropertyData</b> successfully retrieves the property data, the routine writes the property type value to this variable. This value indicates the type of property data that is in the <i>Data</i> buffer.


## -returns



<b>IoGetDeviceInterfacePropertyData</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer that <i>Data</i> points to is too small to contain the property data. *<i>RequiredSize</i> contains the required buffer length.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The specified LCID value is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
The specified property is not supported.

</td>
</tr>
</table>
 




## -remarks



Kernel-mode drivers use the <b>IoGetDeviceInterfacePropertyData</b> routine to retrieve device interface properties that are defined as part of the <a href="https://msdn.microsoft.com/51105f84-38d8-4005-a3fd-4beccc0a2a39">unified device property model</a>. For more information about device interface properties, see <a href="https://msdn.microsoft.com/f41040c5-0eac-450d-b532-9165c543cc1a">Device Properties</a>.

Drivers can use the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439388">IoSetDeviceInterfacePropertyData</a> routine to modify a device interface property.

Callers of <b>IoGetDeviceInterfacePropertyData</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543546">DEVPROPTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439388">IoSetDeviceInterfacePropertyData</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetDeviceInterfacePropertyData routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

