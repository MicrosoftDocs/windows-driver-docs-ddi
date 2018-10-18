---
UID: NF:wudfddi.IWDFDevice.CommitPnpState
title: IWDFDevice::CommitPnpState
author: windows-driver-content
description: The CommitPnpState method commits the state of the Plug and Play (PnP) property (that is, turns on, turns off, or sets to the default state) that the IWDFDevice::SetPnpState method set.
old-location: wdf\iwdfdevice_commitpnpstate.htm
tech.root: wdf
ms.assetid: 650ad98a-81e5-4ec8-b276-a5dc79366652
ms.date: 2/26/2018
ms.keywords: CommitPnpState, CommitPnpState method, CommitPnpState method,IWDFDevice interface, IWDFDevice interface,CommitPnpState method, IWDFDevice.CommitPnpState, IWDFDevice::CommitPnpState, UMDFDeviceObjectRef_51342f9e-fc5f-4100-8c5c-bc58d7569529.xml, umdf.iwdfdevice_commitpnpstate, wdf.iwdfdevice_commitpnpstate, wudfddi/IWDFDevice::CommitPnpState
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDevice.CommitPnpState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::CommitPnpState


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CommitPnpState</b> method commits the state of the Plug and Play (PnP) property (that is, turns on, turns off, or sets to the default state) that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a> method set.


## -parameters






## -returns



None




## -remarks



The values of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561434">WDF_PNP_STATE</a> enumeration identify the state of PnP for the device.


#### Examples

For a code example of how to use the <b>CommitPnpState</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561434">WDF_PNP_STATE</a>
 

 

