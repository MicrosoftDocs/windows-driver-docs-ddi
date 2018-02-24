---
UID: NF:wdtf.IWDTFTarget2.GetValueString
title: IWDTFTarget2::GetValueString method
author: windows-driver-content
description: Returns a string value from the target that is associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluestring.htm
old-project: dtf
ms.assetid: 430de835-6301-40db-b4fe-4eabff0c9b58
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: Microsoft.WDTF.IWDTFTarget2.GetValueString, IWDTFTarget2::GetValueString, GetValueString, Microsoft::WDTF::IWDTFTarget2::GetValueString, dtf.iwdtftarget2_getvaluestring, GetValueString method [Windows Device Testing Framework], IWDTFTarget2 interface, wdtf/IWDTFTarget2::GetValueString, IWDTFTarget2 interface [Windows Device Testing Framework], GetValueString method, IWDTFTarget2, GetValueString method [Windows Device Testing Framework]
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
-	IWDTFTarget2.GetValueString
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFTarget2::GetValueString method


## -description


Returns a string value from the target that is associated with a specified attribute.


## -syntax


````
HRESULT GetValueString(
  [in]          BSTR SDEL,
  [out, retval] BSTR *pValue
);
````


## -parameters




### -param SDEL [in]

An SDEL statement that specifies the attribute value to retrieve.


### -param pValue [out, retval]

The address of a variable that receives the result of this method.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



You specify the field that the<b> GetValueString</b> method retrieves 
by using a regular <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueString</b> 
to work properly. 




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTarget2::GetValueString method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

