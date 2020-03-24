---
UID: NF:wdfpdo.WdfPdoInitSetDefaultLocale
title: WdfPdoInitSetDefaultLocale function (wdfpdo.h)
description: The WdfPdoInitSetDefaultLocale method sets a device's default locale.
old-location: wdf\wdfpdoinitsetdefaultlocale.htm
tech.root: wdf
ms.assetid: d3c068dd-d09c-4b3a-be96-c1c55b3ebfe4
ms.date: 02/26/2018
keywords: ["WdfPdoInitSetDefaultLocale function"]
ms.keywords: DFDeviceObjectFdoPdoRef_12f9db03-8d4b-4ce4-9cde-0081884c6b9c.xml, WdfPdoInitSetDefaultLocale, WdfPdoInitSetDefaultLocale method, kmdf.wdfpdoinitsetdefaultlocale, wdf.wdfpdoinitsetdefaultlocale, wdfpdo/WdfPdoInitSetDefaultLocale
f1_keywords:
 - "wdfpdo/WdfPdoInitSetDefaultLocale"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfPdoInitSetDefaultLocale
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoInitSetDefaultLocale function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoInitSetDefaultLocale</b> method sets a device's default locale.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param LocaleId [in]

A locale identifier (LCID) that represents the default locale. For more information, see <a href="https://docs.microsoft.com/windows/desktop/Intl/locale-identifiers">Locale Identifiers</a>.


## -remarks



When the system requests device description text from a driver, it specifies a locale. If text for the specified locale is not available, the framework returns device text for the driver's default locale.

The driver must call <b>WdfPdoInitSetDefaultLocale</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example sets a device's default locale to United States English (0x409).

```cpp
WdfPdoInitSetDefaultLocale(
                           pDeviceInit,
                           0x409
                           );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitadddevicetext">WdfPdoInitAddDeviceText</a>
 

 

