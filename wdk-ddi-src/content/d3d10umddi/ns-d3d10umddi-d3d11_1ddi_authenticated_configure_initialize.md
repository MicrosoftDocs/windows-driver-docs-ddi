---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
author: windows-driver-content
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_AUTHENTICATED_CONFIGURE_INITIALIZE.
old-location: display\d3d11_1ddi_authenticated_configure_initialize.htm
old-project: display
ms.assetid: 7a087c7b-3ce7-4054-9880-9940ce589fa4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE, D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE structure [Display Devices], display.d3d11_1ddi_authenticated_configure_initialize, D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE, D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
apiname:
-	D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
product: Windows
targetos: Windows
req.typenames: D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE structure


## -description


Contains input data for a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_AUTHENTICATED_CONFIGURE_INITIALIZE</b>.


## -syntax


````
typedef struct D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE {
  D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT Parameters;
  UINT                                     StartSequenceQuery;
  UINT                                     StartSequenceConfigure;
} D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE;
````


## -struct-fields




### -field Parameters

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data.


### -field StartSequenceQuery

The initial sequence number for queries.


### -field StartSequenceConfigure

The initial sequence number for commands.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

