---
UID: NF:wdtf.IWDTFTarget2.get_Context
title: IWDTFTarget2::get_Context method
author: windows-driver-content
description: Gets and sets a name-value pair that represents user data for the target.
old-location: dtf\iwdtftarget2_context.htm
old-project: dtf
ms.assetid: e7a19b73-3393-4ab4-a967-c00b46f81a9e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Context property [Windows Device Testing Framework], Context property [Windows Device Testing Framework], IWDTFTarget2 interface, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], Context property, IWDTFTarget2.Context, IWDTFTarget2::get_Context, IWDTFTarget2::put_Context, Microsoft.WDTF.IWDTFTarget2.Context, Microsoft::WDTF::IWDTFTarget2::Context, dtf.iwdtftarget2_context, get_Context,IWDTFTarget2.get_Context, ntddk/IWDTFTarget2::Context, ntddk/IWDTFTarget2::get_Context, ntddk/IWDTFTarget2::put_Context
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: WDTF.h
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
-	IWDTFTarget2.Context
-	IWDTFTarget2.get_Context
-	IWDTFTarget2.put_Context
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFTarget2::get_Context method


## -description


Gets and sets a name-value pair that represents user data for the target.

This property is read/write.


## -syntax


````
HRESULT put_Context(
  [in]          BSTR    Tag,
  [in]          VARIANT newVal
);

HRESULT get_Context(
  [in]          BSTR    Tag,
  [out, retval] VARIANT *pVal
);
````


## -parameters


## -remarks



The <b>Context</b> property is parameterized with the 
<b>BSTR </b><i>Tag </i>parameter. This parameterization 
enables you to attach many different named values to an instance of the 
<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a> interface. 
You can then retrieve these same values by name at a later time. 

Each value is stored as a <b>VARIANT</b>, which correctly 
follows COM ref-counting rules. You can store object references within the target as 
easily as any other variable data-type.

For more information about the <b>Context</b> property, 
see <a href="https://msdn.microsoft.com/f9e3de20-28be-40c6-802c-f4637b3f6c20">Creating WDTF Scenarios</a>.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTarget2::Context property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

