---
UID: NF:spbcx.SPB_TRANSFER_DESCRIPTOR_INIT
title: SPB_TRANSFER_DESCRIPTOR_INIT function
author: windows-driver-content
description: The SPB_TRANSFER_DESCRIPTOR_INIT function initializes an SPB_TRANSFER_DESCRIPTOR structure.
old-location: spb\spb_transfer_descriptor_init.htm
old-project: SPB
ms.assetid: 96A069B5-BD89-4B8E-88D9-57944F4C9DB8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SPB_TRANSFER_DESCRIPTOR_INIT
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
req.alt-api: SPB_TRANSFER_DESCRIPTOR_INIT
req.alt-loc: Spbcx.h
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
req.typenames: *PSPB_REQUEST_TYPE, SPB_REQUEST_TYPE
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
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406218">SPB_TRANSFER_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_DESCRIPTOR_INIT function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

