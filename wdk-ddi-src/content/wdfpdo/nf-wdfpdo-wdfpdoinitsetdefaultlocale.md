---
UID: NF:wdfpdo.WdfPdoInitSetDefaultLocale
title: WdfPdoInitSetDefaultLocale function
author: windows-driver-content
description: The WdfPdoInitSetDefaultLocale method sets a device's default locale.
old-location: wdf\wdfpdoinitsetdefaultlocale.htm
old-project: wdf
ms.assetid: d3c068dd-d09c-4b3a-be96-c1c55b3ebfe4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfPdoInitSetDefaultLocale
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfPdoInitSetDefaultLocale
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: ChildDeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# WdfPdoInitSetDefaultLocale function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitSetDefaultLocale</b> method sets a device's default locale.



## -syntax

````
VOID WdfPdoInitSetDefaultLocale(
  _In_ PWDFDEVICE_INIT DeviceInit,
  _In_ LCID            LocaleId
);
````


## -parameters

### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param LocaleId [in]

A locale identifier (LCID) that represents the default locale. For more information, see <a href="https://msdn.microsoft.com/ea45b0e5-7df7-47fb-8dad-fccfbe53fec0">Locale Identifiers</a>.


## -returns
None


## -remarks
When the system requests device description text from a driver, it specifies a locale. If text for the specified locale is not available, the framework returns device text for the driver's default locale.

The driver must call <b>WdfPdoInitSetDefaultLocale</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

The following code example sets a device's default locale to United States English (0x409).


## -see-also
<dl>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitadddevicetext.md">WdfPdoInitAddDeviceText</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoInitSetDefaultLocale method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

