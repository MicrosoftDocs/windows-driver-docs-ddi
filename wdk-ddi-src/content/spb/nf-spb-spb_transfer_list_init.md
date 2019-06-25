---
UID: NF:spb.SPB_TRANSFER_LIST_INIT
title: SPB_TRANSFER_LIST_INIT function (spb.h)
description: The SPB_TRANSFER_LIST_INIT function initializes an SPB_TRANSFER_LIST structure.
old-location: spb\spb_transfer_list_init.htm
tech.root: SPB
ms.assetid: 7FFFB495-7E6A-465C-AE93-B62957179531
ms.date: 04/30/2018
ms.keywords: SPB.spb_transfer_list_init, SPB_TRANSFER_LIST_INIT, SPB_TRANSFER_LIST_INIT function [Buses], spb/SPB_TRANSFER_LIST_INIT
ms.topic: function
req.header: spb.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Spb.h
api_name:
- SPB_TRANSFER_LIST_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# SPB_TRANSFER_LIST_INIT function


## -description


The <b>SPB_TRANSFER_LIST_INIT</b> function initializes an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spb/ns-spb-spb_transfer_list">SPB_TRANSFER_LIST</a> structure.


## -parameters




### -param TransferList [out]

A pointer to the <b>SPB_TRANSFER_LIST</b> structure that is to be initialized.


### -param TransferCount [in]

The number of entries in the transfer list. The function writes this value to the <b>TransferCount</b> member of the  <b>SPB_TRANSFER_LIST</b> structure.


## -returns



None.




## -remarks



To initialize the elements in the <b>SPB_TRANSFER_LIST</b> structure's <b>Transfers</b> array, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spb/nf-spb-spb_transfer_list_entry_init_simple">SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spb/nf-spb-spb_transfer_list_entry_init_non_paged">SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spb/nf-spb-spb_transfer_list_entry_init_buffer_list">SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spb/ns-spb-spb_transfer_list">SPB_TRANSFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spb/nf-spb-spb_transfer_list_entry_init_buffer_list">SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spb/nf-spb-spb_transfer_list_entry_init_non_paged">SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/spb/nf-spb-spb_transfer_list_entry_init_simple">SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE</a>
 

 

