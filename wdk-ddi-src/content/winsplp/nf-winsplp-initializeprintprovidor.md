---
UID: NF:winsplp.InitializePrintProvidor
title: InitializePrintProvidor function (winsplp.h)
description: Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location: print\initializeprintprovidor.htm
tech.root: print
ms.assetid: 54a5009d-9893-4766-b9fd-7e7474b55949
ms.date: 04/20/2018
ms.keywords: InitializePrintProvidor, InitializePrintProvidor function [Print Devices], print.initializeprintprovidor, spoolfnc_b67588a9-bccb-4181-8fd0-cbdc1b7af7c5.xml, winsplp/InitializePrintProvidor
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
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
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	InitializePrintProvidor
product:
- Windows
targetos: Windows
req.typenames: 
---

# InitializePrintProvidor function


## -description


<div class="alert"><b>Warning</b>  <p class="note">Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

</div><div> </div>A print provider's <b>InitializePrintProvidor</b> function initializes the provider and supplies the print spooler with the provider's entry points.


## -parameters




### -param pPrintProvidor [out]

Caller-supplied address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560993">PRINTPROVIDOR</a> structure, to be filled in by the print provider.


### -param cbPrintProvidor [in]

Caller-supplied size, in bytes, of the PRINTPROVIDOR structure pointed to by <i>pPrintProvidor</i>.


### -param pFullRegistryPath [in, optional]

Caller-supplied pointer to a string representing the full registry path to the provider's registry entry.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. Otherwise the function should return <b>FALSE</b>.




## -remarks



Print providers are required to define an <b>InitializePrintProvidor</b> function, which is the first function called by the spooler after the provider has been loaded. The function must fill the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff560993">PRINTPROVIDOR</a> structure with pointers to the provider's defined functions (see <a href="https://msdn.microsoft.com/4fae4b69-ed4b-47b6-b6e8-41733aed51a5">Functions Defined by Print Providers</a>). The function can also perform other provider-specific initialization operations.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560993">PRINTPROVIDOR</a>
 

 

