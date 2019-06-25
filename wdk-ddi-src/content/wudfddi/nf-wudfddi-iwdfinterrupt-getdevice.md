---
UID: NF:wudfddi.IWDFInterrupt.GetDevice
title: IWDFInterrupt::GetDevice (wudfddi.h)
description: The GetDevice method returns the framework device object interface for this interrupt object.
old-location: wdf\iwdfinterrupt_getdevice.htm
tech.root: wdf
ms.assetid: 71C4E02F-B58A-46BA-A6A7-133D6CAF2A85
ms.date: 02/26/2018
ms.keywords: GetDevice, GetDevice method, GetDevice method,IWDFInterrupt interface, IWDFInterrupt interface,GetDevice method, IWDFInterrupt.GetDevice, IWDFInterrupt::GetDevice, umdf.iwdfinterrupt_getdevice, wdf.iwdfinterrupt_getdevice, wudfddi/IWDFInterrupt::GetDevice
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFInterrupt.GetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFInterrupt::GetDevice


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDevice</b> method returns the framework device object interface for this interrupt object.


## -parameters






## -returns



<b>GetDevice</b> returns a pointer to the framework device object interface.




## -remarks



For more information about handling interrupts in UMDF drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-hardware-and-handling-interrupts">Accessing Hardware and Handling Interrupts</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfinterrupt">IWDFInterrupt</a>
 

 

