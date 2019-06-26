---
UID: NF:bdasup.BdaStartChanges
title: BdaStartChanges function (bdasup.h)
description: The BdaStartChanges function initiates the setting of new BDA topology changes.
old-location: stream\bdastartchanges.htm
tech.root: stream
ms.assetid: ee54b382-7b69-4d8d-8728-fe2bff7884cf
ms.date: 04/23/2018
ms.keywords: BdaStartChanges, BdaStartChanges function [Streaming Media Devices], bdaref_16498957-566e-405d-b573-3a2eb75a6bcb.xml, bdasup/BdaStartChanges, stream.bdastartchanges
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Bdasup.lib
- Bdasup.dll
api_name:
- BdaStartChanges
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaStartChanges function


## -description


The <b>BdaStartChanges</b> function initiates the setting of new BDA topology changes. 


## -parameters




### -param pIrp






#### - Irp [in]

Points to the IRP for the request to initiate changes. The BDA minidriver receives this IRP with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-start-changes">KSMETHOD_BDA_START_CHANGES</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaStartChanges</b> function to initiate the setting of new BDA topology changes after the minidriver receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-start-changes">KSMETHOD_BDA_START_CHANGES</a> request of the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a> method set from the network provider. BDA minidrivers define dispatch and filter-automation tables so that those minidrivers either dispatch the <b>BdaStartChanges</b> function directly or intercept this request using an internal method (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>), which then calls the <b>BdaStartChanges</b> function. For example, BDA minidrivers that intercept this request can obtain a pointer to the BDA filter from the passed IRP so that they can subsequently reset pending filter resources to the new requirements and set the change state of the filter to BDA_CHANGES_COMPLETE. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/changing-bda-filter-properties">Changing BDA Filter Properties</a> for more information. 

Calling the <b>BdaStartChanges</b> function causes any previously requested topology changes that have not yet been committed to be ignored.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff556518(v=vs.85)">BDA_CHANGE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdacommitchanges">BdaCommitChanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-start-changes">KSMETHOD_BDA_START_CHANGES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>
 

 

