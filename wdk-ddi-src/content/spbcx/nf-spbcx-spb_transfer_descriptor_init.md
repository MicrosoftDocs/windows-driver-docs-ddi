---
UID: NF:spbcx.SPB_TRANSFER_DESCRIPTOR_INIT
title: SPB_TRANSFER_DESCRIPTOR_INIT function
author: windows-driver-content
description: The SPB_TRANSFER_DESCRIPTOR_INIT function initializes an SPB_TRANSFER_DESCRIPTOR structure.
old-location: spb\spb_transfer_descriptor_init.htm
old-project: SPB
ms.assetid: 96A069B5-BD89-4B8E-88D9-57944F4C9DB8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SPB.spb_transfer_descriptor_init, SPB_TRANSFER_DESCRIPTOR_INIT, SPB_TRANSFER_DESCRIPTOR_INIT function [Buses], spbcx/SPB_TRANSFER_DESCRIPTOR_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
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
req.irql: Any IRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Spbcx.h
api_name:
-	SPB_TRANSFER_DESCRIPTOR_INIT
product: Windows
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SPB_TRANSFER_DESCRIPTOR_INIT function


## -description


The <b>SPB_TRANSFER_DESCRIPTOR_INIT</b> function initializes an  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406218">SPB_TRANSFER_DESCRIPTOR</a> structure.


## -syntax


````
VOID SPB_TRANSFER_DESCRIPTOR_INIT(
  _Out_ SPB_TRANSFER_DESCRIPTOR *Descriptor
);
````


## -parameters




### -param Descriptor [out]

A pointer to the <b>SPB_TRANSFER_DESCRIPTOR</b> structure that is to be initialized.


## -returns



None.




## -remarks



Your SPB controller driver must use this function to initialize an <b>SPB_TRANSFER_DESCRIPTOR</b> structure before passing this structure as an output parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a> method. This method writes the transfer parameters for an individual transfer in an I/O transfer sequence to this structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406218">SPB_TRANSFER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a>



 

 


