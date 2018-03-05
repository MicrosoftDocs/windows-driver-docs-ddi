---
UID: NF:prdrvcom.ConvertPrintTicketToDevMode
title: ConvertPrintTicketToDevMode function
author: windows-driver-content
description: The IPrintTicketProvider::ConvertPrintTicketToDevMode method converts a print ticket to a DEVMODEW structure.
old-location: print\iprintticketprovider_convertprinttickettodevmode.htm
old-project: print
ms.assetid: 59457b51-5ab5-4e20-a608-a71c799eeeb9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ConvertPrintTicketToDevMode, ConvertPrintTicketToDevMode method [Print Devices], ConvertPrintTicketToDevMode method [Print Devices], IPrintTicketProvider interface, IPrintTicketProvider interface [Print Devices], ConvertPrintTicketToDevMode method, IPrintTicketProvider::ConvertPrintTicketToDevMode, prdrvcom/IPrintTicketProvider::ConvertPrintTicketToDevMode, print.iprintticketprovider_convertprinttickettodevmode, print_ticket-package_5d7b3ff3-0c39-4896-986a-ae2306543644.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prdrvcom.h
req.include-header: Prdrvcom.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prdrvcom.h
api_name:
-	IPrintTicketProvider.ConvertPrintTicketToDevMode
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# ConvertPrintTicketToDevMode function


## -description


The <code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> method converts a print ticket to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. 


## -syntax


````
HRESULT ConvertPrintTicketToDevMode(
  [in]  IXMLDOMDocument2 *pPrintTicket,
  [in]  ULONG            cbDevmodeIn,
  [in]  PDEVMODE         pDevmodeIn,
  [out] ULONG            *pcbDevmodeOut,
  [out] PDEVMODE         *ppDevmodeOut
);
````


## -parameters




### -param pPrintTicket [in]

A pointer to the input print ticket. <code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> converts the settings in the input print ticket into fields in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


### -param cbDevmodeIn [in]

The size, in bytes, of the input DEVMODEW structure. This size includes both the public and private sections of the DEVMODEW structure. 


### -param pDevmodeIn [in]

A pointer to the input DEVMODEW structure, which contains default settings. The DEVMODEW structure can be the print queue default DEVMODEW structure, or it can be the user default DEVMODEW structure. Because this parameter can represent the user default DEVMODEW structure, the OEM plug-in provider must validate the data in that  structure. A user default DEVMODEW structure might not be valid for a specific driver, for example, when the print queue's driver changes or is upgraded.


### -param pcbDevmodeOut [out]

A pointer to a variable that contains the size, in bytes, of the output <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


### -param ppDevmodeOut [out]

A pointer to a variable that contains the address of the output DEVMODEW structure. When <code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> successfully returns, the members of the output DEVMODEW structure will be reset to reflect the settings in the print ticket. For more information, see the following Remarks section.


## -returns



<code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



The core driver calls the <code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> method before it performs its part of the conversion of a print ticket to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. In the call to this method, the core driver passes an input print ticket that is fully populated and a DEVMODEW structure that is set to default values. In the conversion, the plug-in must undo any changes that it made to the print ticket during the previous conversion from a DEVMODEW structure to a print ticket. If, during this previous conversion, the plug-in moved a feature from a private namespace to the public namespace, the plug-in must restore the feature to the private namespace in a format that is suitable for the core driver, that is, to the format in which the core driver had previously placed the feature in the print ticket that was provided to the plug-in in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553161">IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</a> method. This restoration is necessary so that the core driver can recognize a feature in the print ticket and reflect its settings in the private portion of the core driver's DEVMODEW structure while the core driver performs its part of the print ticket-to-DEVMODEW conversion.

Before the system converts a print ticket back to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure, it first loads the default DEVMODEW. The system then calls the provider's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554354">IPrintTicketProvider::BindPrinter</a> method. This method should then read all of the settings that it supported from the print ticket, and place those settings into the DEVMODEW structure. Note that not all of the features necessarily will be represented, and that often Option instances that are present might not contain all of the Scored Property instances that the provider would normally populate. If the provider makes any changes to the settings that were populated by the system during conversion from print ticket to DEVMODEW, the provider should perform the reverse of that change in this method. After the provider returns, the system then overwrites any public DEVMODEW settings that are represented in the print ticket but that are not explicitly disabled by the provider.




## -see-also

<a href="https://msdn.microsoft.com/4eb3c193-377b-4e51-a97b-50c6fdaa1b08">IPrintTicketProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554360">IPrintTicketProvider::ConvertDevModeToPrintTicket</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintTicketProvider::ConvertPrintTicketToDevMode method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

