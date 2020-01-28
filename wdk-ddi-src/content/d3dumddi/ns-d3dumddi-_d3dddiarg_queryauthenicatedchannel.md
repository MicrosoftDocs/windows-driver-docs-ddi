---
UID: NS:d3dumddi._D3DDDIARG_QUERYAUTHENICATEDCHANNEL
title: _D3DDDIARG_QUERYAUTHENICATEDCHANNEL (d3dumddi.h)
description: The D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure describes authenticated-channel information to query by using the QueryAuthenticatedChannel function.
old-location: display\d3dddiarg_queryauthenticatedchannel.htm
tech.root: display
ms.assetid: d816b4d7-cc99-4a83-9fd2-c7c0659d0318
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_QUERYAUTHENTICATEDCHANNEL, D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure [Display Devices], UMDisplayDriver_param_Structs_5c16c40f-b8b6-41cc-9f83-f204d7213760.xml, _D3DDDIARG_QUERYAUTHENICATEDCHANNEL, d3dumddi/D3DDDIARG_QUERYAUTHENTICATEDCHANNEL, display.d3dddiarg_queryauthenticatedchannel
f1_keywords:
 - "d3dumddi/D3DDDIARG_QUERYAUTHENTICATEDCHANNEL"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_QUERYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
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
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_QUERYAUTHENTICATEDCHANNEL
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_QUERYAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_QUERYAUTHENICATEDCHANNEL structure


## -description


The D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure describes authenticated-channel information to query by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel">QueryAuthenticatedChannel</a> function. 


## -struct-fields




### -field InputSize

[in] The size, in bytes, of the input data that the <b>pInputData</b> member points to. 


### -field pInputData

[in] A pointer to a buffer that describes the information to query. The buffer that <b>pInputData</b> points to is defined identically to the input buffer that is passed to the <b>IDirect3DAuthenticatedChannel::Query</b> method. For more information about <b>IDirect3DAuthenticatedChannel::Query</b>, see the Windows SDK documentation. 


### -field OutputSize

[in] The size, in bytes, of the output data that the <b>pOutputData</b> member points to. 


### -field pOutputData

[in/out] A pointer to a buffer that describes the information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel">QueryAuthenticatedChannel</a> function returns. The buffer that <b>pOutputData</b> points to is defined identically to the output buffer that the <b>IDirect3DAuthenticatedChannel::Query</b> method returns. 


## -remarks



The definitions of the input and output buffers to which the <b>pInputData</b> and <b>pOutputData</b> members point, depend on the type of information. The first member of the input buffer is always a D3DAUTHENTICATEDCHANNEL_QUERY_INPUT structure, whose <b>QueryType</b> member identifies the type of information to query.

The definition of the output buffer also depends on the information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel">QueryAuthenticatedChannel</a> function queries. However, the first member of the output buffer is always a D3DAUTHENTICATEDCHANNEL_QUERY_OUTPUT structure, whose members specify the following information:

<ul>
<li>
The <b>omac</b> member identifies the One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) that permits the caller to authenticate the entire buffer, which prevents man-in-the-middle attacks.

</li>
<li>
The <b>QueryType</b>, <b>hChannel</b>, and <b>SequenceNumber</b> members from the input buffer prevent against replay attacks. 

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel">QueryAuthenticatedChannel</a>
 

 

