---
UID: NF:wdm.IoGetDevicePropertyData
title: IoGetDevicePropertyData function
author: windows-driver-content
description: The IoGetDevicePropertyData routine retrieves the current setting for a device property.
old-location: kernel\iogetdevicepropertydata.htm
old-project: kernel
ms.assetid: 3ca026b8-abed-409c-8be4-01553cfadca3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k104_85cb50ca-43cc-401a-8ed1-32ff0c381ed8.xml, kernel.iogetdevicepropertydata, IoGetDevicePropertyData, wdm/IoGetDevicePropertyData, IoGetDevicePropertyData routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetDevicePropertyData
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetDevicePropertyData function


## -description


The <b>IoGetDevicePropertyData</b> routine retrieves the current setting for a device property.


## -syntax


````
NTSTATUS IoGetDevicePropertyData(
  _In_             PDEVICE_OBJECT Pdo,
  _In_       const DEVPROPKEY     *PropertyKey,
  _In_             LCID           Lcid,
  _Reserved_       ULONG          Flags,
  _In_             ULONG          Size,
  _Out_            PVOID          Data,
  _Out_            PULONG         RequiredSize,
  _Out_            PDEVPROPTYPE   Type
);
````


## -parameters




### -param Pdo [in]

A pointer to the physical device object (PDO) for the device that is being queried.


### -param PropertyKey [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> structure that specifies the device property key.


### -param Lcid [in]

A locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>. The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>. For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/en-us/library/cc233968(PROT.10).aspx">LCID Structure</a>.


### -param Flags

Reserved for system use. Drivers should set this value to 0.


### -param Size [in]

The size, in bytes, of the buffer that <i>Data</i> points to.


### -param Data [out]

A pointer to the device property data.


### -param RequiredSize [out]

A pointer to a ULONG to receive the size of the property information that is returned at <i>Data</i>. If <b>IoGetDevicePropertyData</b> returns STATUS_BUFFER_TOO_SMALL, the caller can use this value to allocate a buffer of the correct size.


### -param Type [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543546">DEVPROPTYPE</a> value. If <b>IoGetDevicePropertyData</b> completes successfully, the routine uses <i>Type</i> to supply the type of data that is returned in the <i>Data</i> buffer.


## -returns



<b>IoGetDevicePropertyData</b> returns an NTSTATUS value. This routine might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded. The <i>Data</i> buffer contains the retrieved data. *<i>Type</i> contains the type of the retrieved data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>Data</i> buffer is too small. *<i>RequiredSize</i> contains the required buffer length.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified device property was not found.

</td>
</tr>
</table>
 




## -remarks



Kernel-mode drivers use the <b>IoGetDevicePropertyData</b> routine to retrieve device properties that are defined as part of the unified device property model. For more information about device properties, see <a href="https://msdn.microsoft.com/f41040c5-0eac-450d-b532-9165c543cc1a">Device Properties</a>.

Drivers can use the <a href="..\wdm\nf-wdm-iosetdevicepropertydata.md">IoSetDevicePropertyData</a> routine to modify a device property.

Callers of <b>IoGetDevicePropertyData</b> must be running at IRQL &lt;= APC_LEVEL in the context of a system thread.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543546">DEVPROPTYPE</a>



<a href="..\wdm\nf-wdm-iosetdevicepropertydata.md">IoSetDevicePropertyData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetDevicePropertyData routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

