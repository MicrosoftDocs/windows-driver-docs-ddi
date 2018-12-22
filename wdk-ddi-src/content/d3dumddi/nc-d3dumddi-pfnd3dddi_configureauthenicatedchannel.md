---
UID: NC:d3dumddi.PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL
title: PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL
description: The ConfigureAuthenticatedChannel function sets state within an authenticated channel.
old-location: display\configureauthenticatedchannel.htm
tech.root: display
ms.assetid: 95485e96-fa4f-4c88-b88b-97b79f507abd
ms.date: 05/10/2018
ms.keywords: ConfigureAuthenticatedChannel, ConfigureAuthenticatedChannel callback function [Display Devices], PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL, PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL callback, UserModeDisplayDriver_Functions_183c7dec-91c3-4929-a86d-c648d1b59ceb.xml, d3dumddi/ConfigureAuthenticatedChannel, display.configureauthenticatedchannel
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: ConfigureAuthenticatedChannel is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	ConfigureAuthenticatedChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL callback function


## -description


The <b>ConfigureAuthenticatedChannel</b> function sets state within an authenticated channel. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542913">D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL</a> structure that describes how to configure an authenticated channel. This structure contains an input buffer that describes how to configure the authenticated channel and an output buffer with configuration information. 


## -returns



<b>ConfigureAuthenticatedChannel</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The authenticated channel is successfully configured. | 
| **E_OUTOFMEMORY** | [ConfigureAuthenticatedChannel](https://msdn.microsoft.com/95485e96-fa4f-4c88-b88b-97b79f507abd)  could not allocate the required memory for it to complete. | 


## -remarks



The input buffer contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) that the driver must authenticate. The input buffer also contains the driver's handle to the authenticated channel, a sequence number, and a GUID that indicates the configuration type.

The driver should fail <b>ConfigureAuthenticatedChannel</b> if the input OMAC does not match, if the sequence number is not greater than a sequence number that was specified in a previous call, or if the sequence number has not yet been initialized (the exception to this last rule is for the initialization call itself). 

The driver should duplicate the input data in the structure of the output buffer and should sign the output structure identically to how it currently handles <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) queries.

Except for those situations in which the application incorrectly specifies an output buffer that is too small, the driver should always place the return code in the output structure. Therefore, the application has a secure mechanism to determine the return code. 

<b>ConfigureAuthenticatedChannel</b> performs different operations depending on each of following GUIDs that is specified in the input structure. The driver should fail if the input buffer size does not match the size that is defined for the specified GUID. 






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542913">D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL</a>
 

 

