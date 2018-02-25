---
UID: NF:wudfddi.IWDFDevice.CommitPnpState
title: IWDFDevice::CommitPnpState method
author: windows-driver-content
description: The CommitPnpState method commits the state of the Plug and Play (PnP) property (that is, turns on, turns off, or sets to the default state) that the IWDFDevice::SetPnpState method set.
old-location: wdf\iwdfdevice_commitpnpstate.htm
old-project: wdf
ms.assetid: 650ad98a-81e5-4ec8-b276-a5dc79366652
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, C, CommitPnpState method, CommitPnpState method, IWDFDevice interface, CommitPnpState,IWDFDevice.CommitPnpState, D, F, I, IWDFDevice, IWDFDevice interface, CommitPnpState method, IWDFDevice::CommitPnpState, P, S, UMDFDeviceObjectRef_51342f9e-fc5f-4100-8c5c-bc58d7569529.xml, W, a, c, e, i, m, n, o, p, t, umdf.iwdfdevice_commitpnpstate, v, wdf.iwdfdevice_commitpnpstate, wudfddi/IWDFDevice::CommitPnpState"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDevice.CommitPnpState
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice::CommitPnpState method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CommitPnpState</b> method commits the state of the Plug and Play (PnP) property (that is, turns on, turns off, or sets to the default state) that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a> method set.


## -syntax


````
void CommitPnpState();
````


## -parameters






## -returns



None




## -remarks



The values of the <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_state.md">WDF_PNP_STATE</a> enumeration identify the state of PnP for the device.


#### Examples

For a code example of how to use the <b>CommitPnpState</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>.

<div class="code"></div>



## -see-also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_pnp_state.md">WDF_PNP_STATE</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::CommitPnpState method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

