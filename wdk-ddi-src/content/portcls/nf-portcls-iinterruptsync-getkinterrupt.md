---
UID: NF:portcls.IInterruptSync.GetKInterrupt
title: IInterruptSync::GetKInterrupt (portcls.h)
description: The GetKInterrupt method gets a WDM interrupt object from a port-class synchronization object.
old-location: audio\iinterruptsync_getkinterrupt.htm
tech.root: audio
ms.assetid: 045c509b-852d-405c-9615-8a2f351bf8c7
ms.date: 05/08/2018
ms.keywords: GetKInterrupt, GetKInterrupt method [Audio Devices], GetKInterrupt method [Audio Devices],IInterruptSync interface, IInterruptSync interface [Audio Devices],GetKInterrupt method, IInterruptSync.GetKInterrupt, IInterruptSync::GetKInterrupt, audio.iinterruptsync_getkinterrupt, audmp-routines_7782adef-dc02-4876-bd48-812f8b3e58da.xml, portcls/IInterruptSync::GetKInterrupt
f1_keywords:
 - "portcls/IInterruptSync.GetKInterrupt"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IInterruptSync.GetKInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# IInterruptSync::GetKInterrupt


## -description


The <code>GetKInterrupt</code> method gets a WDM interrupt object from a port-class synchronization object.


## -returns



<code>GetKInterrupt</code> returns a pointer to a WDM interrupt object.




## -remarks



The PKINTERRUPT pointer is one of the two parameters that are passed to every interrupt service routine (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a>). Every <b>IInterruptSync</b> object has an associated PKINTERRUPT pointer. It points to the associated kernel interrupt object, which is opaque.

A driver typically calls <code>GetKInterrupt</code> only if it needs to obtain this pointer so that it can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesynchronizeexecution">KeSynchronizeExecution</a> directly.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iinterruptsync">IInterruptSync</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesynchronizeexecution">KeSynchronizeExecution</a>
 

 

