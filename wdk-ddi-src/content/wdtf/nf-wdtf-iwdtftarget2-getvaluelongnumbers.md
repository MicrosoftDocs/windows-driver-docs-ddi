---
UID: NF:wdtf.IWDTFTarget2.GetValueLongNumbers
title: IWDTFTarget2::GetValueLongNumbers (wdtf.h)
description: Returns a collection of long number values from the target that are associated with a specified attribute.
old-location: dtf\iwdtftarget2_getvaluelongnumbers.htm
tech.root: dtf
ms.assetid: 178a28be-b592-45a7-8d46-47cbf9904fc6
ms.date: 04/04/2018
ms.keywords: GetValueLongNumbers, GetValueLongNumbers method [Windows Device Testing Framework], GetValueLongNumbers method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],GetValueLongNumbers method, IWDTFTarget2.GetValueLongNumbers, IWDTFTarget2::GetValueLongNumbers, Microsoft.WDTF.IWDTFTarget2.GetValueLongNumbers, Microsoft::WDTF::IWDTFTarget2::GetValueLongNumbers, dtf.iwdtftarget2_getvaluelongnumbers, wdtf/IWDTFTarget2::GetValueLongNumbers
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
-	IWDTFTarget2.GetValueLongNumbers
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTarget2::GetValueLongNumbers


## -description


Returns a collection of long number values from the target that are associated with a specified attribute.


## -parameters




### -param SDEL [in]

An SDEL statement that specifies the attribute value to retrieve.


### -param ppValue [out, retval]

The address of a variable that receives the result of this method.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



You specify the field that the<b> GetValueLongNumbers</b> method retrieves 
by using a regular <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">SDEL</a> 
statement. Typically, an SDEL statement can contain comparison operators and value specifiers to 
perform matches. However, you do not need these items for <b>GetValueLongNumbers</b> 
to work properly. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>
 

 

