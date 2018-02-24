---
UID: NF:wdtf.IWDTFDeviceDepot2.get__NewEnum
title: IWDTFDeviceDepot2::get__NewEnum method
author: windows-driver-content
description: Gets a new iteration variable that the For Each loop structure implicitly uses.
old-location: dtf\iwdtfdevicedepot2__newenum.htm
old-project: dtf
ms.assetid: cc864595-a0bb-4fd4-9d93-830e8fd6a346
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_NewEnum property [Windows Device Testing Framework], get__NewEnum, Microsoft.WDTF.IWDTFDeviceDepot2._NewEnum, wdtf/IWDTFDeviceDepot2::_NewEnum, IWDTFDeviceDepot2._NewEnum, IWDTFDeviceDepot2::get__NewEnum, IWDTFDeviceDepot2, dtf.iwdtfdevicedepot2__newenum, IWDTFDeviceDepot2 interface [Windows Device Testing Framework], _NewEnum property, _NewEnum property [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, IWDTFActions2, wdtf/IWDTFDeviceDepot2::get__NewEnum, Microsoft::WDTF::IWDTFDeviceDepot2::_NewEnum, IWDTFActions2::get__NewEnum"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
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
-	IWDTFDeviceDepot2._NewEnum
-	IWDTFDeviceDepot2.get__NewEnum
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDeviceDepot2::get__NewEnum method


## -description


Gets a new iteration variable that the <b>For Each</b> 
loop structure implicitly uses.

This property is read-only.


## -syntax


````
HRESULT get__NewEnum(
  [out, retval] IUnknown **ppNewEnum
);
````


## -parameters


## -remarks



You cannot access the <b>_NewEnum</b> property from the 
JScript programming language.

You must use the Active Template Library (ATL) to implement this functionality. 
For more information about how ATL implements this functionality, see the 
<b>ICollectionOnSTLImpl </b>interface in the MSDN Library.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDeviceDepot2::_NewEnum property%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

