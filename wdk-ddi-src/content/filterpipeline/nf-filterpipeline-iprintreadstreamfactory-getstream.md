---
UID: NF:filterpipeline.IPrintReadStreamFactory.GetStream
title: IPrintReadStreamFactory::GetStream (filterpipeline.h)
description: The GetStream method gets the stream interface.
old-location: print\iprintreadstreamfactory_getstream.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintReadStreamFactory::GetStream"]
ms.keywords: GetStream, GetStream method [Print Devices], GetStream method [Print Devices],IPrintReadStreamFactory interface, IPrintReadStreamFactory interface [Print Devices],GetStream method, IPrintReadStreamFactory.GetStream, IPrintReadStreamFactory::GetStream, filterpipeline/IPrintReadStreamFactory::GetStream, filterpipeline_0e4b4a26-da03-4719-bbce-2bb160a882e2.xml, print.iprintreadstreamfactory_getstream
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintReadStreamFactory::GetStream
 - filterpipeline/IPrintReadStreamFactory::GetStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPrintReadStreamFactory.GetStream
---

# IPrintReadStreamFactory::GetStream


## -description

The `GetStream` method gets the stream interface.

## -parameters

### -param ppStream 

[out]
A pointer to an [IPrintReadStream](./nn-filterpipeline-iprintreadstream.md) interface. The filter can use this interface to read the contents of the print ticket.

## -returns

`GetStream` returns an **HRESULT** value.

## -remarks

The following code example shows how a filter can use **IPrintReadStreamFactory** to access the per-user print ticket.

```cpp
VARIANT var;
VariantInit(&var);

HRESULT hr = pIPropertyBag->GetProperty(
  XPS_FP_USER_PRINT_TICKET,
  &var);

if (SUCCEEDED(hr))
{
 IPrintReadStreamFactory   *pPrintReadStreamFactory;

 hr = V_UNKNOWN(&var)->QueryInterface(
 IID_IPrintReadStreamFactory,
 reinterpret_cast<void **>(&pPrintReadStreamFactory));

 if (SUCCEEDED(hr))
    {
 IPrintReadStream *pPrintTicketStream;

 hr = pPrintReadStreamFactory->GetStream(&pPrintTicketStream);

 if (SUCCEEDED(hr))
      {

       // Use the print ticket here.
       // It's OK to cache the pointer
       // to use now and release later.

 pPrintTicketStream->Release();
      }

 pPrintReadStreamFactory->Release();
    }

 VariantClear(&var);
}
```
