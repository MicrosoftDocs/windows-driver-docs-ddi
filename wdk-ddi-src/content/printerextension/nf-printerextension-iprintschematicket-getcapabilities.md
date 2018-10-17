---
UID: NF:printerextension.IPrintSchemaTicket.GetCapabilities
title: IPrintSchemaTicket::GetCapabilities
author: windows-driver-content
description: Gets an IPrintSchemaCapabilities object that represents the printer capabilities based on the current settings of this IPrintSchemaTicket object.
old-location: print\iprintschematicket_getcapabilities.htm
tech.root: print
ms.assetid: 5556BD5E-6489-4CCF-8C62-DDA53AD9F368
ms.date: 4/20/2018
ms.keywords: GetCapabilities, GetCapabilities method [Print Devices], GetCapabilities method [Print Devices],IPrintSchemaTicket interface, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],GetCapabilities method, IPrintSchemaTicket.GetCapabilities, IPrintSchemaTicket::GetCapabilities, print.iprintschematicket_getcapabilities, printerextension/IPrintSchemaTicket::GetCapabilities
ms.topic: method
req.header: printerextension.h
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	printerextension.h
api_name:
-	IPrintSchemaTicket.GetCapabilities
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaTicket::GetCapabilities


## -description


Gets an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a> object.


## -parameters




### -param ppCapabilities






#### - ppPrintCapabilities [out, retval]

The returned <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



Because this method retrieves a new PrintCapabilities document every time it is invoked, it is recommended that you invoke this method only when the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a> object has been modified.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>



<a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>



<a href="https://msdn.microsoft.com/C22BC037-05D2-4F44-8704-D1D56909B603">IPrintSchemaFeature::SelectedOption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>



<a href="https://msdn.microsoft.com/DF788C8F-DA60-47F1-83DB-2E1947E41142">IPrintSchemaTicket::put_JobCopiesAllDocuments</a>
 

 

