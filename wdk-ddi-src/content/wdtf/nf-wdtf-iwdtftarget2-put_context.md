---
UID: NF:wdtf.IWDTFTarget2.put_Context
title: IWDTFTarget2::put_Context (wdtf.h)
description: Gets and sets a name-value pair that represents user data for the target.
old-location: dtf\iwdtftarget2_context.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFTarget2::put_Context"]
ms.keywords: Context property [Windows Device Testing Framework], Context property [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],Context property, IWDTFTarget2.Context, IWDTFTarget2.put_Context, IWDTFTarget2::Context, IWDTFTarget2::get_Context, IWDTFTarget2::put_Context, Microsoft.WDTF.IWDTFTarget2.Context, Microsoft::WDTF::IWDTFTarget2::Context, dtf.iwdtftarget2_context, ntddk/IWDTFTarget2::Context, ntddk/IWDTFTarget2::get_Context, ntddk/IWDTFTarget2::put_Context, put_Context
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFTarget2::put_Context
 - wdtf/IWDTFTarget2::put_Context
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFTarget2::put_Context
---

# IWDTFTarget2::put_Context


## -description

Gets and sets a name-value pair that represents user data for the target.

This property is read/write.

## -parameters

## -remarks

The <b>Context</b> property is parameterized with the 
<b>BSTR </b><i>Tag </i>parameter. This parameterization 
enables you to attach many different named values to an instance of the 
<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> interface. 
You can then retrieve these same values by name at a later time. 

Each value is stored as a <b>VARIANT</b>, which correctly 
follows COM ref-counting rules. You can store object references within the target as 
easily as any other variable data-type.

For more information about the <b>Context</b> property, 
see <a href="/windows-hardware/drivers/wdtf/creating-wdtf-scenarios">Creating WDTF Scenarios</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>

