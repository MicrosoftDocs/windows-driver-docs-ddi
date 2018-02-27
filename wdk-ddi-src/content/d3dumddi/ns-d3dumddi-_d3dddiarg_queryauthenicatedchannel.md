---
UID: NS:d3dumddi._D3DDDIARG_QUERYAUTHENICATEDCHANNEL
title: "_D3DDDIARG_QUERYAUTHENICATEDCHANNEL"
author: windows-driver-content
description: The D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure describes authenticated-channel information to query by using the QueryAuthenticatedChannel function.
old-location: display\d3dddiarg_queryauthenticatedchannel.htm
old-project: display
ms.assetid: d816b4d7-cc99-4a83-9fd2-c7c0659d0318
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDIARG_QUERYAUTHENTICATEDCHANNEL, D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure [Display Devices], UMDisplayDriver_param_Structs_5c16c40f-b8b6-41cc-9f83-f204d7213760.xml, _D3DDDIARG_QUERYAUTHENICATEDCHANNEL, d3dumddi/D3DDDIARG_QUERYAUTHENTICATEDCHANNEL, display.d3dddiarg_queryauthenticatedchannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_QUERYAUTHENTICATEDCHANNEL
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_QUERYAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_QUERYAUTHENICATEDCHANNEL structure


## -description


The D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure describes authenticated-channel information to query by using the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel</a> function. 


## -syntax


````
typedef struct _D3DDDIARG_QUERYAUTHENTICATEDCHANNEL {
  UINT       InputSize;
  const VOID *pInputData;
  UINT       OutputSize;
  VOID       *pOutputData;
} D3DDDIARG_QUERYAUTHENTICATEDCHANNEL;
````


## -struct-fields




### -field InputSize

[in] The size, in bytes, of the input data that the <b>pInputData</b> member points to. 


### -field pInputData

[in] A pointer to a buffer that describes the information to query. The buffer that <b>pInputData</b> points to is defined identically to the input buffer that is passed to the <b>IDirect3DAuthenticatedChannel::Query</b> method. For more information about <b>IDirect3DAuthenticatedChannel::Query</b>, see the Windows SDK documentation. 


### -field OutputSize

[in] The size, in bytes, of the output data that the <b>pOutputData</b> member points to. 


### -field pOutputData

[in/out] A pointer to a buffer that describes the information that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel</a> function returns. The buffer that <b>pOutputData</b> points to is defined identically to the output buffer that the <b>IDirect3DAuthenticatedChannel::Query</b> method returns. 


## -remarks



The definitions of the input and output buffers to which the <b>pInputData</b> and <b>pOutputData</b> members point, depend on the type of information. The first member of the input buffer is always a D3DAUTHENTICATEDCHANNEL_QUERY_INPUT structure, whose <b>QueryType</b> member identifies the type of information to query.

The definition of the output buffer also depends on the information that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel</a> function queries. However, the first member of the output buffer is always a D3DAUTHENTICATEDCHANNEL_QUERY_OUTPUT structure, whose members specify the following information:

<ul>
<li>
The <b>omac</b> member identifies the One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) that permits the caller to authenticate the entire buffer, which prevents man-in-the-middle attacks.

</li>
<li>
The <b>QueryType</b>, <b>hChannel</b>, and <b>SequenceNumber</b> members from the input buffer prevent against replay attacks. 

</li>
</ul>



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_QUERYAUTHENTICATEDCHANNEL structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

