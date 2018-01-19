---
UID: NE:wudfddi_types._WDF_PNP_STATE
title: _WDF_PNP_STATE
author: windows-driver-content
description: The WDF_PNP_STATE enumeration contains values that identify the status of Plug and Play (PnP) for a device.
old-location: wdf\wdf_pnp_state.htm
old-project: wdf
ms.assetid: f17a6d52-5f68-470c-9f45-6a175e0fbf01
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_PNP_STATE, WDF_PNP_STATE
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
req.alt-api: WDF_PNP_STATE
req.alt-loc: Wudfddi_types.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: WDF_PNP_STATE
req.product: Windows 10 or later.
---

# _WDF_PNP_STATE enumeration



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PNP_STATE</b> enumeration contains values that identify the status of Plug and Play (PnP) for a device.



## -syntax

````
typedef enum _WDF_PNP_STATE { 
  WdfPnpStateInvalid           = 0,
  WdfPnpStateDisabled          = 1,
  WdfPnpStateFailed            = 2,
  WdfPnpStateRemoved           = 3,
  WdfPnpStateResourcesChanged  = 4,
  WdfPnpStateDontDisplayInUI   = 5,
  WdfPnpStateNotDisableable    = 6,
  WdfPnpStateMaximum           = ( WdfPnpStateNotDisableable + 1 )
} WDF_PNP_STATE;
````


## -enum-fields

### -field WdfPnpStateInvalid

The PnP state for the device is invalid.


### -field WdfPnpStateDisabled

The device is disabled.


### -field WdfPnpStateFailed

The device is present but has failed.


### -field WdfPnpStateRemoved

The device has been removed. 


### -field WdfPnpStateResourcesChanged

The device's resource requirements have changed.


### -field WdfPnpStateDontDisplayInUI

The device is hidden (not displayed) in Device Manager.


### -field WdfPnpStateNotDisableable

The device cannot be disabled.


### -field WdfPnpStateMaximum

Valid enumeration values were exceeded.


## -remarks
A UMDF driver supplies one of the values of <b>WDF_PNP_STATE</b> to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558834">IWDFDevice::GetPnpState</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a> method to identify the PnP property to retrieve or set status for.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558834">IWDFDevice::GetPnpState</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_PNP_STATE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

