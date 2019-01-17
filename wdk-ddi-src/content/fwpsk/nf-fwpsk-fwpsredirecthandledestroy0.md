---
UID: NF:fwpsk.FwpsRedirectHandleDestroy0
title: FwpsRedirectHandleDestroy0 function
description: The FwpsRedirectHandleDestroy0 function destroys a redirect handle that was previously created by calling the FwpsRedirectHandleCreate0 function.Note  FwpsRedirectHandleDestroy0 is a specific version of FwpsRedirectHandleDestroy.
old-location: netvista\fwpsredirecthandledestroy0.htm
tech.root: netvista
ms.assetid: 0859c9bb-04f2-4bef-9da7-da72375d05f7
ms.date: 05/02/2018
ms.keywords: FwpsRedirectHandleDestroy0, FwpsRedirectHandleDestroy0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsRedirectHandleDestroy0, netvista.fwpsredirecthandledestroy0
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsRedirectHandleDestroy0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsRedirectHandleDestroy0 function


## -description


The <b>FwpsRedirectHandleDestroy0</b> function destroys a redirect handle that was previously created by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439681">FwpsRedirectHandleCreate0</a> function.<div class="alert"><b>Note</b>  <b>FwpsRedirectHandleDestroy0</b> is a specific version of <b>FwpsRedirectHandleDestroy</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param redirectHandle

The redirect handle being destroyed.




## -returns



None.




## -remarks




    A callout driver calls the <b>FwpsRedirectHandleDestroy0</b> function to destroy a redirect handle that the callout driver previously created by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439681">FwpsRedirectHandleCreate0</a> function. 


   




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439681">FwpsRedirectHandleCreate0</a>
 

 

