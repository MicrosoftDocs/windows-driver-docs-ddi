---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.PublishPrintTicketHelperInterface
title: IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface (prcomoem.h)
description: The IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface method publishes the print ticket helper interface for either Unidrv or Pscript5 user interface (UI) plug-ins.
tech.root: print
ms.date: 08/22/2022
keywords: ["IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface"]
ms.keywords: IPrintOemPrintTicketProvider interface [Print Devices],PublishPrintTicketHelperInterface method, IPrintOemPrintTicketProvider.PublishPrintTicketHelperInterface, IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface, PublishPrintTicketHelperInterface, PublishPrintTicketHelperInterface method [Print Devices], PublishPrintTicketHelperInterface method [Print Devices],IPrintOemPrintTicketProvider interface, prcomoem/IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface, print.iprintoemprintticketprovider_publishprinttickethelperinterface, print_ticket-package_b314b169-8111-4320-89fc-a99fb6e30639.xml
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface
 - prcomoem/IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface
---

## -description

The **IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface** method publishes the print ticket helper interface for either Unidrv or Pscript5 user interface (UI) plug-ins.

## -parameters

### -param pHelper [in]

A pointer to an **IUnknown** interface, which should be cast to one of the following interfaces: For Unidrv plug-ins, the print ticket helper interface is **IPrintCoreHelperUni**; for Pscript5 plug-ins, the print ticket helper interface is **IPrintCoreHelperPS**.

## -returns

**IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface** should return **S_OK** if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

If the plug-in maintains a handle to the helper object, the plug-in is responsible for later releasing that handle when it is no longer needed.

If **IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface**  uses the helper interface, it should cache a pointer to the interface, and increment the reference count (by means of a call to the interface's **AddRef** method). If this method successfully increments the reference count, it should return **S_OK**.
