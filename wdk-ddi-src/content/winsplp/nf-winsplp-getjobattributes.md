---
UID: NF:winsplp.GetJobAttributes
title: GetJobAttributes function
author: windows-driver-content
description: Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location: print\getjobattributes.htm
old-project: print
ms.assetid: 06affa2e-d22c-4d24-8c5f-6ef52e3051fa
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: GetJobAttributes
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
req.alt-api: GetJobAttributes
req.alt-loc: Spoolss.dll
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
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# GetJobAttributes function



## -description

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

Caller-supplied pointer to an <a href="..\winddiui\ns-winddiui-_attribute_info_3.md">ATTRIBUTE_INFO_3</a> structure that receives information about the print job.


## -returns
<b>GetJobAttributes</b> returns <b>TRUE</b> if it is successful in obtaining the print job attributes; otherwise it returns <b>FALSE</b>.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a>
</dt>
<dt>
<a href="..\winddiui\ns-winddiui-_attribute_info_3.md">ATTRIBUTE_INFO_3</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-getjobattributesex.md">GetJobAttributesEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GetJobAttributes function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

