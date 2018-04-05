---
UID: NF:wdfpdo.WdfPdoInitSetDefaultLocale
title: WdfPdoInitSetDefaultLocale function
author: windows-driver-content
description: The WdfPdoInitSetDefaultLocale method sets a device's default locale.
old-location: wdf\wdfpdoinitsetdefaultlocale.htm
old-project: wdf
ms.assetid: d3c068dd-d09c-4b3a-be96-c1c55b3ebfe4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_12f9db03-8d4b-4ce4-9cde-0081884c6b9c.xml, WdfPdoInitSetDefaultLocale, WdfPdoInitSetDefaultLocale method, kmdf.wdfpdoinitsetdefaultlocale, wdf.wdfpdoinitsetdefaultlocale, wdfpdo/WdfPdoInitSetDefaultLocale
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfPdoInitSetDefaultLocale
product:
- Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# WdfPdoInitSetDefaultLocale function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitSetDefaultLocale</b> method sets a device's default locale.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param LocaleId [in]

A locale identifier (LCID) that represents the default locale. For more information, see <a href="https://msdn.microsoft.com/ea45b0e5-7df7-47fb-8dad-fccfbe53fec0">Locale Identifiers</a>.


## -returns



None




## -remarks



When the system requests device description text from a driver, it specifies a locale. If text for the specified locale is not available, the framework returns device text for the driver's default locale.

The driver must call <b>WdfPdoInitSetDefaultLocale</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example sets a device's default locale to United States English (0x409).

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfPdoInitSetDefaultLocale(
                           pDeviceInit,
                           0x409
                           );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548780">WdfPdoInitAddDeviceText</a>
 

 

