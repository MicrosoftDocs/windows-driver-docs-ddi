---
UID: NE:wudfddi_types._WDF_PNP_CAPABILITY
title: "_WDF_PNP_CAPABILITY"
author: windows-driver-content
description: The WDF_PNP_CAPABILITY enumeration contains values that identify Plug and Play (PnP) capabilities for a device.
old-location: wdf\wdf_pnp_capability.htm
old-project: wdf
ms.assetid: adcc5f64-b49c-47ca-8ef9-276537a0d7c6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, A, B, C, D, F, I, L, N, P, T, W, WDF_PNP_CAPABILITY, WDF_PNP_CAPABILITY enumeration, WdfPnpCapDockDevice, WdfPnpCapEjectSupported, WdfPnpCapInvalid, WdfPnpCapLockSupported, WdfPnpCapMaximum, WdfPnpCapNoDisplayInUI, WdfPnpCapRemovable, WdfPnpCapSurpriseRemovalOk, Y, _, _WDF_PNP_CAPABILITY, umdf.wdf_pnp_capability, umdfstructs_365aedf9-fb60-49db-8925-bc6cf0d9a9d6.xml, wdf.wdf_pnp_capability, wudfddi_types/WDF_PNP_CAPABILITY, wudfddi_types/WdfPnpCapDockDevice, wudfddi_types/WdfPnpCapEjectSupported, wudfddi_types/WdfPnpCapInvalid, wudfddi_types/WdfPnpCapLockSupported, wudfddi_types/WdfPnpCapMaximum, wudfddi_types/WdfPnpCapNoDisplayInUI, wudfddi_types/WdfPnpCapRemovable, wudfddi_types/WdfPnpCapSurpriseRemovalOk"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_types.h
apiname:
-	WDF_PNP_CAPABILITY
product: Windows
targetos: Windows
req.typenames: WDF_PNP_CAPABILITY
req.product: Windows 10 or later.
---

# _WDF_PNP_CAPABILITY enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PNP_CAPABILITY</b> enumeration contains values that identify Plug and Play (PnP) capabilities for a device.


## -syntax


````
typedef enum _WDF_PNP_CAPABILITY { 
  WdfPnpCapInvalid            = 0,
  WdfPnpCapLockSupported      = 1,
  WdfPnpCapEjectSupported     = 2,
  WdfPnpCapRemovable          = 3,
  WdfPnpCapDockDevice         = 4,
  WdfPnpCapSurpriseRemovalOk  = 5,
  WdfPnpCapNoDisplayInUI      = 6,
  WdfPnpCapMaximum            = ( WdfPnpCapNoDisplayInUI + 1 )
} WDF_PNP_CAPABILITY;
````


## -enum-fields




### -field WdfPnpCapInvalid

Indicates whether PnP capabilities of the device are invalid.


### -field WdfPnpCapLockSupported

Indicates whether the device can be locked in its slot to prevent ejection. (Setting this capability disables ejecting a device from its slot and does not disable ejecting media from a device.) 


### -field WdfPnpCapEjectSupported

Indicates whether the device can be ejected from its slot. (Setting this capability enables ejecting a device from its slot and does not enable ejecting media from a device.) 


### -field WdfPnpCapRemovable

Indicates whether the device can be removed while the computer is running. If <b>WdfPnpCapRemovable</b> is set to <b>WdfTrue</b> and <b>WdfPnpCapSurpriseRemovalOk</b> is set to <b>WdfFalse</b>, users should use the system's Unplug or Eject Hardware application. 


### -field WdfPnpCapDockDevice

Indicates whether the device is a docking station. 


### -field WdfPnpCapSurpriseRemovalOk

Indicates whether users can remove the device without using the computer's Unplug or Eject Hardware application.


### -field WdfPnpCapNoDisplayInUI

Indicates whether the device can be hidden (not displayed) in Device Manager.


### -field WdfPnpCapMaximum

Valid enumeration values were exceeded.


## -remarks



A UMDF driver supplies one of the values of <b>WDF_PNP_CAPABILITY</b> to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556974">IWDFDeviceInitialize::GetPnpCapability</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556993">IWDFDeviceInitialize::SetPnpCapability</a> method to identify the PnP capability to retrieve or set status for.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556974">IWDFDeviceInitialize::GetPnpCapability</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556993">IWDFDeviceInitialize::SetPnpCapability</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_PNP_CAPABILITY enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

