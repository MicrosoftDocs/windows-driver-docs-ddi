---
UID: NS:hbapiwmi._AddTarget_IN
title: "_AddTarget_IN"
author: windows-driver-content
description: The AddPort_IN structure is used by a WMI client to deliver the input parameter data of the AddTarget WMI method to the HBA miniport driver.
old-location: storage\addtarget_in.htm
tech.root: storage
ms.assetid: 7c6a7ca8-83aa-41fe-92f5-6598464d9803
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PAddTarget_IN, AddTarget_IN, AddTarget_IN structure [Storage Devices], PAddTarget_IN, PAddTarget_IN structure pointer [Storage Devices], _AddTarget_IN, hbapiwmi/AddTarget_IN, hbapiwmi/PAddTarget_IN, storage.addtarget_in, structs-Fibre_7109b51c-872e-4e2e-affb-388fe21750d7.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	AddTarget_IN
product:
- Windows
targetos: Windows
req.typenames: AddTarget_IN, *PAddTarget_IN
---

# _AddTarget_IN structure


## -description


The AddPort_IN structure is used by a WMI client to deliver the input parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550136">AddTarget</a> WMI method to the HBA miniport driver.


## -struct-fields




### -field HbaPortWWN

Contains the worldwide name of the local port whose events the WMI client will receive. 


### -field DiscoveredPortWWN

Contains a worldwide name that specifies the discovered target whose events the WMI client will receive.


### -field AllTargets

Indicates the scope of the target events to report. If this member is zero, the WMI client will receive events associated with the port that is indicated by <i>DiscoveredPortWWN</i>. If this member is nonzero, the WMI client will all events associated with all currently discovered targets as well as targets that are discovered in the future. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550136">AddTarget</a>
 

 

