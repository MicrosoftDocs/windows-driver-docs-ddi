---
UID: NF:filterpipeline.IPrintReadStreamFactory.GetStream
title: IPrintReadStreamFactory::GetStream (filterpipeline.h)
description: The GetStream method gets the stream interface.
old-location: print\iprintreadstreamfactory_getstream.htm
tech.root: print
ms.assetid: 47447f00-a57d-4821-b10e-1b2cf7eaad94
ms.date: 04/20/2018
ms.keywords: GetStream, GetStream method [Print Devices], GetStream method [Print Devices],IPrintReadStreamFactory interface, IPrintReadStreamFactory interface [Print Devices],GetStream method, IPrintReadStreamFactory.GetStream, IPrintReadStreamFactory::GetStream, filterpipeline/IPrintReadStreamFactory::GetStream, filterpipeline_0e4b4a26-da03-4719-bbce-2bb160a882e2.xml, print.iprintreadstreamfactory_getstream
ms.topic: method
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- filterpipeline.h
api_name:
- IPrintReadStreamFactory.GetStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintReadStreamFactory::GetStream


## -description


The <code>GetStream</code> method gets the stream interface.


## -parameters




### -param ppStream [out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554337">IPrintReadStream</a> interface. The filter can use this interface to read the contents of the print ticket.


## -returns



<code>GetStream</code> returns an <b>HRESULT</b> value.




## -remarks



The following code example shows how a filter can use <b>IPrintReadStreamFactory</b> to access the per-user print ticket.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VARIANT var;
VariantInit(&var);

HRESULT hr = pIPropertyBag->GetProperty(
  XPS_FP_USER_PRINT_TICKET,
  &var);

if (SUCCEEDED(hr))
{
 IPrintReadStreamFactory   *pPrintReadStreamFactory;

 hr = V_UNKNOWN(&var)->QueryInterface(
 IID_IPrintReadStreamFactory,
 reinterpret_cast&lt;void **>(&pPrintReadStreamFactory));

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
}</pre>
</td>
</tr>
</table></span></div>


