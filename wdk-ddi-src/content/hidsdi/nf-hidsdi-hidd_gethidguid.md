---
UID: NF:hidsdi.HidD_GetHidGuid
title: HidD_GetHidGuid function (hidsdi.h)
description: The HidD_GetHidGuid routine returns the device interfaceGUID for HIDClass devices.
old-location: hid\hidd_gethidguid.htm
tech.root: hid
ms.assetid: 552b607e-65c7-4595-9adb-b9c2f4301afd
ms.date: 04/30/2018
keywords: ["HidD_GetHidGuid function"]
ms.keywords: HidD_GetHidGuid, HidD_GetHidGuid routine [Human Input Devices], hid.hidd_gethidguid, hidfunc_61242b6f-b794-48c7-84b8-ef8d0d4e69af.xml, hidsdi/HidD_GetHidGuid
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HidD_GetHidGuid
 - hidsdi/HidD_GetHidGuid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_GetHidGuid
---

# HidD_GetHidGuid function


## -description

The <b>HidD_GetHidGuid</b> routine returns the <a href="/windows-hardware/drivers/">device interface</a><a href="/windows-hardware/customize/desktop/unattend/microsoft-windows-shell-setup-notificationarea-promotedicon2-guid">GUID</a> for HIDClass devices.

## -parameters

### -param HidGuid 

[out]
Pointer to a caller-allocated GUID buffer that the routine uses to return the device interface GUID for HIDClass devices.

## -remarks

Only user-mode applications can call <b>HidD_GetHidGuid</b>.

For more information, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceinterfaces">IoGetDeviceInterfaces</a>