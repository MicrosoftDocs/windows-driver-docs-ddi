---
UID: NF:hbaapi.HBA_ResetStatistics
title: HBA_ResetStatistics function
author: windows-driver-content
description: The HBA_ResetStatistics routine resets the statistics counters for the indicated port and HBA.
old-location: storage\hba_resetstatistics.htm
tech.root: storage
ms.assetid: 4e889905-9c5e-446c-8d0e-09e445f7c1a4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_ResetStatistics, HBA_ResetStatistics routine [Storage Devices], fibreHBA_rtns_37577fde-9a33-4fd7-8e80-abbd7458b4ef.xml, hbaapi/HBA_ResetStatistics, storage.hba_resetstatistics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_ResetStatistics
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_ResetStatistics function


## -description


The <b>HBA_ResetStatistics</b> routine resets the statistics counters for the indicated port and HBA. 


## -parameters




### -param Handle

<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/Ff557097(v=VS.85).aspx"><b>HBA_OpenAdapter</b></a> that identifies the HBA on which the port is located.  </p>


### -param PortIndex [in]

Indicates for which port on the HBA the statistics counters should be reset. 


#### - HbaHandle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA on which the port is located.  


## -returns



None




## -remarks



The <b>HBA_ResetStatistics</b> routine serves similar purpose to the <b>ResetStatistics</b> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562501">MSFC_FibrePortHBAMethods WMI Class</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562501">MSFC_FibrePortHBAMethods WMI Class</a>
 

 

