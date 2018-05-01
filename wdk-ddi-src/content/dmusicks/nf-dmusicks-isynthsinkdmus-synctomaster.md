---
UID: NF:dmusicks.ISynthSinkDMus.SyncToMaster
title: ISynthSinkDMus::SyncToMaster
author: windows-driver-content
description: The SyncToMaster method allows synchronization to the master clock in order to avoid drift.
old-location: audio\isynthsinkdmus_synctomaster.htm
old-project: audio
ms.assetid: 5009e4d8-5299-4eeb-a70d-5be87694b1d0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: ISynthSinkDMus interface [Audio Devices],SyncToMaster method, ISynthSinkDMus.SyncToMaster, ISynthSinkDMus::SyncToMaster, SyncToMaster, SyncToMaster method [Audio Devices], SyncToMaster method [Audio Devices],ISynthSinkDMus interface, audio.isynthsinkdmus_synctomaster, audmp-routines_35d431eb-a92c-4e73-b75c-8a3a1f0451ce.xml, dmusicks/ISynthSinkDMus::SyncToMaster
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	ISynthSinkDMus.SyncToMaster
product: Windows
targetos: Windows
req.typenames: 
---

# ISynthSinkDMus::SyncToMaster


## -description


The <code>SyncToMaster</code> method allows synchronization to the master clock in order to avoid drift.


## -parameters




### -param rfTime [in]

Specifies the reference time from the master clock. Reference time is measured in 100-nanosecond units.


### -param fStart [in]

Specifies whether the sample clock is to be reset to zero with this reference time. If <b>TRUE</b>, the sample clock must be reset to zero at time <i>rtTime</i>. If <b>FALSE</b>, the sample clock is not reset.


## -returns



<code>SyncToMaster</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



Because the master time and sample time might be driven by different crystals, they can drift apart. The port driver periodically calls this method to give the miniport driver an opportunity to synchronize its sample clock to the master clock.

Parameter <i>fStart</i> is <b>TRUE</b> during the first call to <code>SyncToMaster</code> after the stream enters the KSSTATE_RUN state (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a>). Otherwise, <i>fStart</i> is <b>FALSE</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537011">ISynthSinkDMus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a>
 

 

