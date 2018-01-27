---
UID: NF:wdm.IoSetDevicePropertyData
title: IoSetDevicePropertyData function
author: windows-driver-content
description: The IoSetDevicePropertyData routine modifies the current setting for a device property.
old-location: kernel\iosetdevicepropertydata.htm
old-project: kernel
ms.assetid: 8e535a6a-9b17-4ef6-b068-43042a589ac0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.iosetdevicepropertydata, k104_a7cd308b-4d43-4364-80fb-ae773d0de101.xml, IoSetDevicePropertyData routine [Kernel-Mode Driver Architecture], IoSetDevicePropertyData, wdm/IoSetDevicePropertyData
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
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoSetDevicePropertyData
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoSetDevicePropertyData function


## -description


The <b>IoSetDevicePropertyData</b> routine modifies the current setting for a device property.


## -syntax


````
NTSTATUS IoSetDevicePropertyData(
  _In_           PDEVICE_OBJECT Pdo,
  _In_     const DEVPROPKEY     *PropertyKey,
  _In_           LCID           Lcid,
  _In_           ULONG          Flags,
  _In_           DEVPROPTYPE    Type,
  _In_           ULONG          Size,
  _In_opt_       PVOID          Data
);
````


## -parameters




### -param Pdo [in]

A pointer to the physical device object (PDO) for the device that is being queried.


### -param PropertyKey [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a> structure that specifies the device property key.


### -param Lcid [in]

A locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>.

The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language).

Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>.

For more information about language-specific LCID values, see <a href="http://msdn.microsoft.com/en-us/library/cc233968(PROT.10).aspx">LCID Structure</a>.


### -param Flags [in]

Set this parameter to <b>PLUGPLAY_PROPERTY_PERSISTENT</b> if the property value set by this routine should persist across computer restarts. Otherwise, set <i>Flags</i> to zero.

Windows 8 and Windows Server 2012 and later operating systems treat <b>Flags</b> as if <b>PLUGPLAY_PROPERTY_PERSISTENT</b>  is always passed.


### -param Type [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff543546">DEVPROPTYPE</a> value that specifies the type of the data that is provided in the <i>Data</i> buffer.


### -param Size [in]

The size, in bytes, of the buffer that <i>Data</i> points to.


### -param Data [in, optional]

A pointer to the device property data. Set this parameter to <b>NULL</b> to delete the specified property. If <i>Data</i> is non-<b>NULL</b>, the routine stores an internal copy of the property value. The buffer pointed to by <i>Data</i> does not need to remain valid after the call returns.


## -returns


<b>IoSetDevicePropertyData</b> returns STATUS_SUCCESS if the call was successful, or the appropriate NTSTATUS code on failure.



## -remarks


Kernel-mode drivers use the <b>IoSetDevicePropertyData</b> routine to modify device properties that are defined as part of the unified device property model. For more information about device properties, see <a href="https://msdn.microsoft.com/f41040c5-0eac-450d-b532-9165c543cc1a">Device Properties</a>.

To delete a property for a specific locale, pass a language-specific LCID value in <i>Lcid</i> and <b>NULL</b> in <i>Data</i>.

To delete a property for all locales, pass <b>LOCALE_NEUTRAL</b> in <i>Lcid</i> and <b>NULL</b> in <i>Data</i>.

To modify a property for a specific locale, pass a language-specific LCID value in <i>Lcid</i> and non-<b>NULL</b> in <i>Data</i>.

To modify a property for all locales, pass <b>LOCALE_NEUTRAL</b> in <i>Lcid</i> and non-<b>NULL</b> in <i>Data</i>.

Beginning with Windows 8 and Windows Server 2012 passing <b>LOCALE_NEUTRAL</b> in <i>Lcid</i> is treated like any other locale.

Drivers can use the <a href="..\wdm\nf-wdm-iogetdevicepropertydata.md">IoGetDevicePropertyData</a> routine to obtain the current value for a device property.

Callers of <b>IoSetDeviceProperty</b> must be running at IRQL &lt;= APC_LEVEL in the context of a system thread.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543546">DEVPROPTYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn315031">DEVPROPKEY</a>

<a href="..\wdm\nf-wdm-iogetdevicepropertydata.md">IoGetDevicePropertyData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetDevicePropertyData routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

