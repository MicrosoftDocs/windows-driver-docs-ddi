---
UID: NF:winsplp.GetJobAttributes
title: GetJobAttributes function
author: windows-driver-content
description: Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location: print\getjobattributes.htm
old-project: print
ms.assetid: 06affa2e-d22c-4d24-8c5f-6ef52e3051fa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetJobAttributes, GetJobAttributes function [Print Devices], print.getjobattributes, spoolfnc_5f511391-a38e-4d0b-8d45-4464b798a7c9.xml, winsplp/GetJobAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: This function is available in Microsoft Windows Server 2003 and later operating system versions.
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	GetJobAttributes
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# GetJobAttributes function


## -description


<div class="alert"><b>Warning</b>  <p class="note">Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

</div><div> </div>A print provider's <b>GetJobAttributes</b> function gets information about a print job.


## -syntax


````
BOOL GetJobAttributes(
  _In_  LPWSTR            pPrinterName,
  _In_  LPDEVMODEW        pDevmode,
  _Out_ PATTRIBUTE_INFO_3 pAttributeInfo
);
````


## -parameters




### -param pPrinterName [in]

Caller-supplied pointer to a NULL-terminated Unicode string containing the printer name.


### -param pDevmode [in]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure that is passed to the print processor or printer driver.


### -param pAttributeInfo [out]

Caller-supplied pointer to an <a href="..\winsplp\ns-winsplp-_attribute_info_3.md">ATTRIBUTE_INFO_3</a> structure that receives information about the print job.


## -returns



<b>GetJobAttributes</b> returns <b>TRUE</b> if it is successful in obtaining the print job attributes; otherwise it returns <b>FALSE</b>.




## -see-also

<a href="..\winsplp\ns-winsplp-_attribute_info_3.md">ATTRIBUTE_INFO_3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a>



<a href="..\winsplp\nf-winsplp-getjobattributesex.md">GetJobAttributesEx</a>



 

 


