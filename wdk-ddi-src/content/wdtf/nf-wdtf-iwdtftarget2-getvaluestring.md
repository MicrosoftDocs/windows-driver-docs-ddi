---
UID: NF:wdtf.IWDTFTarget2.GetValueString
title: IWDTFTarget2::GetValueString
author: windows-driver-content
description: Returns a string value from the target that is associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluestring.htm
tech.root: dtf
ms.assetid: 430de835-6301-40db-b4fe-4eabff0c9b58
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: GetValueString, GetValueString method [Windows Device Testing Framework], GetValueString method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],GetValueString method, IWDTFTarget2.GetValueString, IWDTFTarget2::GetValueString, Microsoft.WDTF.IWDTFTarget2.GetValueString, Microsoft::WDTF::IWDTFTarget2::GetValueString, dtf.iwdtftarget2_getvaluestring, wdtf/IWDTFTarget2::GetValueString
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFTarget2.GetValueString
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTarget2::GetValueString


## -description


Returns a string value from the target that is associated with a specified attribute.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>
 

 

