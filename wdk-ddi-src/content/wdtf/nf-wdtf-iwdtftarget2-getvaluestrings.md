---
UID: NF:wdtf.IWDTFTarget2.GetValueStrings
title: IWDTFTarget2::GetValueStrings method
author: windows-driver-content
description: Returns a collection of string values from the target that are associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluestrings.htm
old-project: dtf
ms.assetid: 2bc18baa-77e0-4ce1-85d9-55817333ecaa
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWDTFTarget2, Microsoft.WDTF.IWDTFTarget2.GetValueStrings, IWDTFTarget2 interface [Windows Device Testing Framework], GetValueStrings method, GetValueStrings, wdtf/IWDTFTarget2::GetValueStrings, GetValueStrings method [Windows Device Testing Framework], IWDTFTarget2 interface, GetValueStrings method [Windows Device Testing Framework], IWDTFTarget2::GetValueStrings, Microsoft::WDTF::IWDTFTarget2::GetValueStrings, dtf.iwdtftarget2_getvaluestrings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTF.Interop.metadata_dll.dll
apiname:
-	IWDTFTarget2.GetValueStrings
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFTarget2::GetValueStrings method


## -description


Returns a collection of string values from the target that are associated 
with a specified attribute.


## -syntax


````
HRESULT GetValueStrings(
  [in]          BSTR          SDEL,
  [out, retval] IWDTFStrings2 **ppValues
);
````


## -parameters




### -param SDEL [in]

An SDEL statement that specifies the attribute value to retrieve.


### -param ppValues [out, retval]

The address of a variable that receives the result of this method.


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -remarks


You specify the field that the<b> GetValueStrings</b> method retrieves 
by using a regular <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueStrings</b> 
to work properly. 



## -see-also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTarget2::GetValueStrings method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

