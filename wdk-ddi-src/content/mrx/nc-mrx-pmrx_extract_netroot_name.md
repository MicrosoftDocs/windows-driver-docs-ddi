---
UID: NC:mrx.PMRX_EXTRACT_NETROOT_NAME
title: PMRX_EXTRACT_NETROOT_NAME
author: windows-driver-content
description: The MRxExtractNetRootName routine is called by RDBSS to request that a network mini-redirector extract the name of the NET_ROOT structure from a given pathname.
old-location: ifsk\mrxextractnetrootname.htm
old-project: ifsk
ms.assetid: e990b7fc-a341-419d-b358-eac4fa2dca78
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: MRxExtractNetRootName, MRxExtractNetRootName routine [Installable File System Drivers], PMRX_EXTRACT_NETROOT_NAME, ifsk.mrxextractnetrootname, mrx/MRxExtractNetRootName, mrxref_6ccbe7d3-a74d-4eab-bfc1-994791d9613a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: mrx.h
req.include-header: Mrx.h
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
-	UserDefined
api_location:
-	mrx.h
api_name:
-	MRxExtractNetRootName
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_EXTRACT_NETROOT_NAME callback function


## -description


The<i> MRxExtractNetRootName</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector extract the name of the NET_ROOT structure from a given pathname. 


## -parameters




### -param FilePathName [in]

A pointer to a Unicode string that contains a pathname. 


### -param SrvCall [in]

A pointer to the SRV_CALL structure. 


### -param NetRootName [out]

On input, a pointer for storing a Unicode string. On success, this parameter will contain a pointer to a Unicode string that contains a NET_ROOT structure name. 


### -param OPTIONAL








#### - RestOfName [out, optional]

A pointer to a Unicode string that contains the rest of the name on success. This parameter is optional and can be a <b>NULL</b> pointer on input.


## -returns



None




## -remarks



<i>MRxExtractNetRootName</i> parses the input name into the SRV_CALL structure, the NET_ROOT structure, and the rest of the pathname.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549864">MRxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549869">MRxCreateVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550653">MRxFinalizeNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550656">MRxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550663">MRxFinalizeVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550750">MRxPreparseName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550824">MRxSrvCallWinnerNotify</a>
 

 

