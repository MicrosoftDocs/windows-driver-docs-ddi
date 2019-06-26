---
UID: NS:d3dumddi._D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL
title: _D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL (d3dumddi.h)
description: The D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure describes the state that is set within an authenticated channel by using the ConfigureAuthenticatedChannel function.
old-location: display\d3dddiarg_configureauthenticatedchannel.htm
tech.root: display
ms.assetid: 8f27fe6d-fe34-4006-a8b1-d2f2190ec044
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL, D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure [Display Devices], UMDisplayDriver_param_Structs_ce65fb22-4c07-4b0f-b0cc-356f0010c88d.xml, _D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL, d3dumddi/D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL, display.d3dddiarg_configureauthenticatedchannel
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
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
- D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL structure


## -description


The D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure describes the state that is set within an authenticated channel by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel">ConfigureAuthenticatedChannel</a> function. 


## -struct-fields




### -field InputSize

[in] The size, in bytes, of the input data that the <b>pInputData</b> member points to. 


### -field pInputData

[in] A pointer to a buffer that describes the configuration data to set. The definition of the input buffer depends on the configuration data that is set. The buffer that <b>pInputData</b> points to is defined identically to the input buffer that is passed to the <b>IDirect3DAuthenticatedChannel::Configure</b> method. For more information about <b>IDirect3DAuthenticatedChannel::Configure</b>, see the Windows SDK documentation. 


### -field pOutputData

[in/out] A pointer to a buffer that describes the information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel">ConfigureAuthenticatedChannel</a> function returns. 


## -remarks



The first member of the input buffer that the <b>pInputData</b> member points to is always the D3DAUTHENTICATEDCHANNEL_CONFIGURE_INPUT structure, whose members specify the following information: 

<ul>
<li>
The <b>ConfigureType</b> member identifies the configuration state to set. 

</li>
<li>
The <b>omac</b> member identifies the One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC), which verifies that the input is from a trusted source.

</li>
<li>
The <b>SequenceNumber</b> member specifies a unique number that the driver can use to prevent against replay attacks. 

</li>
</ul>
The <b>pOutputData</b> member points to a D3DAUTHENTICATEDCHANNEL_CONFIGURE_OUTPUT structure that contains the configuration type and the sequence number of the output buffer to prevent against replay attacks. 

Configuration state that an authenticated channel sets cannot be disabled by another authenticated channel. A call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel">ConfigureAuthenticatedChannel</a> function with such an attempt   fails. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel">ConfigureAuthenticatedChannel</a>
 

 

