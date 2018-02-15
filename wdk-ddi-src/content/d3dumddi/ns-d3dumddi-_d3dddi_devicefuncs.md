---
UID: NS:d3dumddi._D3DDDI_DEVICEFUNCS
title: "_D3DDDI_DEVICEFUNCS"
author: windows-driver-content
description: The D3DDDI_DEVICEFUNCS structure contains functions that the user-mode display driver can implement to render graphics primitives and process state changes.
old-location: display\d3dddi_devicefuncs.htm
old-project: display
ms.assetid: 7345cd67-c10c-46f0-bd56-6f18929f4aa6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_DEVICEFUNCS structure [Display Devices], _D3DDDI_DEVICEFUNCS, d3dumddi/D3DDDI_DEVICEFUNCS, D3D_other_Structs_108deb18-33e2-4a62-9d10-777352fbdd27.xml, D3DDDI_DEVICEFUNCS, display.d3dddi_devicefuncs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	D3DDDI_DEVICEFUNCS
product: Windows
targetos: Windows
req.typenames: D3DDDI_DEVICEFUNCS
---

# _D3DDDI_DEVICEFUNCS structure


## -description


The D3DDDI_DEVICEFUNCS structure contains functions that the user-mode display driver can implement to render graphics primitives and process state changes.


## -syntax


````
typedef struct _D3DDDI_DEVICEFUNCS {
  PFND3DDDI_SETRENDERSTATE                           pfnSetRenderState;
  PFND3DDDI_UPDATEWINFO                              pfnUpdateWInfo;
  PFND3DDDI_VALIDATEDEVICE                           pfnValidateDevice;
  PFND3DDDI_SETTEXTURESTAGESTATE                     pfnSetTextureStageState;
  PFND3DDDI_SETTEXTURE                               pfnSetTexture;
  PFND3DDDI_SETPIXELSHADER                           pfnSetPixelShader;
  PFND3DDDI_SETPIXELSHADERCONST                      pfnSetPixelShaderConst;
  PFND3DDDI_SETSTREAMSOURCEUM                        pfnSetStreamSourceUm;
  PFND3DDDI_SETINDICES                               pfnSetIndices;
  PFND3DDDI_SETINDICESUM                             pfnSetIndicesUm;
  PFND3DDDI_DRAWPRIMITIVE                            pfnDrawPrimitive;
  PFND3DDDI_DRAWINDEXEDPRIMITIVE                     pfnDrawIndexedPrimitive;
  PFND3DDDI_DRAWRECTPATCH                            pfnDrawRectPatch;
  PFND3DDDI_DRAWTRIPATCH                             pfnDrawTriPatch;
  PFND3DDDI_DRAWPRIMITIVE2                           pfnDrawPrimitive2;
  PFND3DDDI_DRAWINDEXEDPRIMITIVE2                    pfnDrawIndexedPrimitive2;
  PFND3DDDI_VOLBLT                                   pfnVolBlt;
  PFND3DDDI_BUFBLT                                   pfnBufBlt;
  PFND3DDDI_TEXBLT                                   pfnTexBlt;
  PFND3DDDI_STATESET                                 pfnStateSet;
  PFND3DDDI_SETPRIORITY                              pfnSetPriority;
  PFND3DDDI_CLEAR                                    pfnClear;
  PFND3DDDI_UPDATEPALETTE                            pfnUpdatePalette;
  PFND3DDDI_SETPALETTE                               pfnSetPalette;
  PFND3DDDI_SETVERTEXSHADERCONST                     pfnSetVertexShaderConst;
  PFND3DDDI_MULTIPLYTRANSFORM                        pfnMultiplyTransform;
  PFND3DDDI_SETTRANSFORM                             pfnSetTransform;
  PFND3DDDI_SETVIEWPORT                              pfnSetViewport;
  PFND3DDDI_SETZRANGE                                pfnSetZRange;
  PFND3DDDI_SETMATERIAL                              pfnSetMaterial;
  PFND3DDDI_SETLIGHT                                 pfnSetLight;
  PFND3DDDI_CREATELIGHT                              pfnCreateLight;
  PFND3DDDI_DESTROYLIGHT                             pfnDestroyLight;
  PFND3DDDI_SETCLIPPLANE                             pfnSetClipPlane;
  PFND3DDDI_GETINFO                                  pfnGetInfo;
  PFND3DDDI_LOCK                                     pfnLock;
  PFND3DDDI_UNLOCK                                   pfnUnlock;
  PFND3DDDI_CREATERESOURCE                           pfnCreateResource;
  PFND3DDDI_DESTROYRESOURCE                          pfnDestroyResource;
  PFND3DDDI_SETDISPLAYMODE                           pfnSetDisplayMode;
  PFND3DDDI_PRESENT                                  pfnPresent;
  PFND3DDDI_FLUSH                                    pfnFlush;
  PFND3DDDI_CREATEVERTEXSHADERFUNC                   pfnCreateVertexShaderFunc;
  PFND3DDDI_DELETEVERTEXSHADERFUNC                   pfnDeleteVertexShaderFunc;
  PFND3DDDI_SETVERTEXSHADERFUNC                      pfnSetVertexShaderFunc;
  PFND3DDDI_CREATEVERTEXSHADERDECL                   pfnCreateVertexShaderDecl;
  PFND3DDDI_DELETEVERTEXSHADERDECL                   pfnDeleteVertexShaderDecl;
  PFND3DDDI_SETVERTEXSHADERDECL                      pfnSetVertexShaderDecl;
  PFND3DDDI_SETVERTEXSHADERCONSTI                    pfnSetVertexShaderConstI;
  PFND3DDDI_SETVERTEXSHADERCONSTB                    pfnSetVertexShaderConstB;
  PFND3DDDI_SETSCISSORRECT                           pfnSetScissorRect;
  PFND3DDDI_SETSTREAMSOURCE                          pfnSetStreamSource;
  PFND3DDDI_SETSTREAMSOURCEFREQ                      pfnSetStreamSourceFreq;
  PFND3DDDI_SETCONVOLUTIONKERNELMONO                 pfnSetConvolutionKernelMono;
  PFND3DDDI_COMPOSERECTS                             pfnComposeRects;
  PFND3DDDI_BLT                                      pfnBlt;
  PFND3DDDI_COLORFILL                                pfnColorFill;
  PFND3DDDI_DEPTHFILL                                pfnDepthFill;
  PFND3DDDI_CREATEQUERY                              pfnCreateQuery;
  PFND3DDDI_DESTROYQUERY                             pfnDestroyQuery;
  PFND3DDDI_ISSUEQUERY                               pfnIssueQuery;
  PFND3DDDI_GETQUERYDATA                             pfnGetQueryData;
  PFND3DDDI_SETRENDERTARGET                          pfnSetRenderTarget;
  PFND3DDDI_SETDEPTHSTENCIL                          pfnSetDepthStencil;
  PFND3DDDI_GENERATEMIPSUBLEVELS                     pfnGenerateMipSubLevels;
  PFND3DDDI_SETPIXELSHADERCONSTI                     pfnSetPixelShaderConstI;
  PFND3DDDI_SETPIXELSHADERCONSTB                     pfnSetPixelShaderConstB;
  PFND3DDDI_CREATEPIXELSHADER                        pfnCreatePixelShader;
  PFND3DDDI_DELETEPIXELSHADER                        pfnDeletePixelShader;
  PFND3DDDI_CREATEDECODEDEVICE                       pfnCreateDecodeDevice;
  PFND3DDDI_DESTROYDECODEDEVICE                      pfnDestroyDecodeDevice;
  PFND3DDDI_SETDECODERENDERTARGET                    pfnSetDecodeRenderTarget;
  PFND3DDDI_DECODEBEGINFRAME                         pfnDecodeBeginFrame;
  PFND3DDDI_DECODEENDFRAME                           pfnDecodeEndFrame;
  PFND3DDDI_DECODEEXECUTE                            pfnDecodeExecute;
  PFND3DDDI_DECODEEXTENSIONEXECUTE                   pfnDecodeExtensionExecute;
  PFND3DDDI_CREATEVIDEOPROCESSDEVICE                 pfnCreateVideoProcessDevice;
  PFND3DDDI_DESTROYVIDEOPROCESSDEVICE                pfnDestroyVideoProcessDevice;
  PFND3DDDI_VIDEOPROCESSBEGINFRAME                   pfnVideoProcessBeginFrame;
  PFND3DDDI_VIDEOPROCESSENDFRAME                     pfnVideoProcessEndFrame;
  PFND3DDDI_SETVIDEOPROCESSRENDERTARGET              pfnSetVideoProcessRenderTarget;
  PFND3DDDI_VIDEOPROCESSBLT                          pfnVideoProcessBlt;
  PFND3DDDI_CREATEEXTENSIONDEVICE                    pfnCreateExtensionDevice;
  PFND3DDDI_DESTROYEXTENSIONDEVICE                   pfnDestroyExtensionDevice;
  PFND3DDDI_EXTENSIONEXECUTE                         pfnExtensionExecute;
  PFND3DDDI_CREATEOVERLAY                            pfnCreateOverlay;
  PFND3DDDI_UPDATEOVERLAY                            pfnUpdateOverlay;
  PFND3DDDI_FLIPOVERLAY                              pfnFlipOverlay;
  PFND3DDDI_GETOVERLAYCOLORCONTROLS                  pfnGetOverlayColorControls;
  PFND3DDDI_SETOVERLAYCOLORCONTROLS                  pfnSetOverlayColorControls;
  PFND3DDDI_DESTROYOVERLAY                           pfnDestroyOverlay;
  PFND3DDDI_DESTROYDEVICE                            pfnDestroyDevice;
  PFND3DDDI_QUERYRESOURCERESIDENCY                   pfnQueryResourceResidency;
  PFND3DDDI_OPENRESOURCE                             pfnOpenResource;
  PFND3DDDI_GETCAPTUREALLOCATIONHANDLE               pfnGetCaptureAllocationHandle;
  PFND3DDDI_CAPTURETOSYSMEM                          pfnCaptureToSysMem;
  PFND3DDDI_LOCKASYNC                                pfnLockAsync;
  PFND3DDDI_UNLOCKASYNC                              pfnUnlockAsync;
  PFND3DDDI_RENAME                                   pfnRename;
  PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR              pfnCreateVideoProcessor;
  PFND3DDDI_DXVAHD_SETVIDEOPROCESSBLTSTATE           pfnSetVideoProcessBltState;
  PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE    pfnGetVideoProcessBltStatePrivate;
  PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE        pfnSetVideoProcessStreamState;
  PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE pfnGetVideoProcessStreamStatePrivate;
  PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD                 pfnVideoProcessBltHD;
  PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR             pfnDestroyVideoProcessor;
  PFND3DDDI_CREATEAUTHENTICATEDCHANNEL               pfnCreateAuthenticatedChannel;
  PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE          pfnAuthenticatedChannelKeyExchange;
  PFND3DDDI_QUERYAUTHENTICATEDCHANNEL                pfnQueryAuthenticatedChannel;
  PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL             pfnConfigureAuthenticatedChannel;
  PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL              pfnDestroyAuthenticatedChannel;
  PFND3DDDI_CREATECRYPTOSESSION                      pfnCreateCryptoSession;
  PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE                 pfnCryptoSessionKeyExchange;
  PFND3DDDI_DESTROYCRYPTOSESSION                     pfnDestroyCryptoSession;
  PFND3DDDI_ENCRYPTIONBLT                            pfnEncryptionBlt;
  PFND3DDDI_GETPITCH                                 pfnGetPitch;
  PFND3DDDI_STARTSESSIONKEYREFRESH                   pfnStartSessionKeyRefresh;
  PFND3DDDI_FINISHSESSIONKEYREFRESH                  pfnFinishSessionKeyRefresh;
  PFND3DDDI_GETENCRYPTIONBLTKEY                      pfnGetEncryptionBltKey;
  PFND3DDDI_DECRYPTIONBLT                            pfnDecryptionBlt;
  PFND3DDDI_RESOLVESHAREDRESOURCE                    pfnResolveSharedResource;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN8)
  PFND3DDDI_VOLBLT1                                  pfnVolBlt1;
  PFND3DDDI_BUFBLT1                                  pfnBufBlt1;
  PFND3DDDI_TEXBLT1                                  pfnTexBlt1;
  PFND3DDDI_DISCARD                                  pfnDiscard;
  PFND3DDDI_OFFERRESOURCES                           pfnOfferResources;
  PFND3DDDI_RECLAIMRESOURCES                         pfnReclaimResources;
  PFND3DDDI_CHECKDIRECTFLIPSUPPORT                   pfnCheckDirectFlipSupport;
  PFND3DDDI_CREATERESOURCE2                          pfnCreateResource2;
  PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT            pfnCheckMultiPlaneOverlaySupport;
  PFND3DDDI_PRESENTMULTIPLANEOVERLAY                 pfnPresentMultiPlaneOverlay;
#endif 
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  void                                               *pfnReserved1;
  PFND3DDDI_FLUSH1                                   pfnFlush1;
  PFND3DDDI_CHECKCOUNTERINFO                         pfnCheckCounterInfo;
  PFND3DDDI_CHECKCOUNTER                             pfnCheckCounter;
  PFND3DDDI_UPDATESUBRESOURCEUP                      pfnUpdateSubresourceUP;
  PFND3DDDI_PRESENT1                                 pfnPresent1;
  PFND3DDDI_CHECKPRESENTDURATIONSUPPORT              pfnCheckPresentDurationSupport;
#endif 
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  PFND3DDDI_SETMARKER                                pfnSetMarker;
  PFND3DDDI_SETMARKERMODE                            pfnSetMarkerMode;
#endif 
} D3DDDI_DEVICEFUNCS;
````


## -struct-fields




### -field pfnSetRenderState

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setrenderstate.md">SetRenderState</a> function that updates the render state.


### -field pfnUpdateWInfo

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updatewinfo.md">UpdateWInfo</a> function that updates the w range for w buffering.


### -field pfnValidateDevice

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_validatedevice.md">ValidateDevice</a> function that returns the number of passes in which the hardware can perform the blending operations that are specified in the current state. 


### -field pfnSetTextureStageState

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_settexturestagestate.md">SetTextureStageState</a> function that updates the state of a texture at a particular stage in a multiple-texture group.


### -field pfnSetTexture

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_settexture.md">SetTexture</a> function that sets a texture to a particular stage in a multiple-texture group.


### -field pfnSetPixelShader

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshader.md">SetPixelShader</a> function that sets the current pixel shader.


### -field pfnSetPixelShaderConst

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconst.md">SetPixelShaderConst</a> function that sets one or more pixel shader constant registers with float values.


### -field pfnSetStreamSourceUm

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setstreamsourceum.md">SetStreamSourceUM</a> function that binds a vertex stream source to a user memory buffer.


### -field pfnSetIndices

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setindices.md">SetIndices</a> function that sets the current index buffer.


### -field pfnSetIndicesUm

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setindicesum.md">SetIndicesUM</a> function that binds an index buffer to a user memory buffer.


### -field pfnDrawPrimitive

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a> function that draws nonindexed primitives in which the Microsoft Direct3D runtime has not transformed the vertex data.


### -field pfnDrawIndexedPrimitive

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive.md">DrawIndexedPrimitive</a> function that draws indexed primitives in which the Direct3D runtime has not transformed the vertex data.


### -field pfnDrawRectPatch

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawrectpatch.md">DrawRectPatch</a> function that draws a new or cached rectangular patch or updates the specification of a previously defined patch.


### -field pfnDrawTriPatch

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawtripatch.md">DrawTriPatch</a> function that draws a new or cached triangular patch or updates the specification of a previously defined patch.


### -field pfnDrawPrimitive2

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive2.md">DrawPrimitive2</a> function that draws nonindexed primitives in which the Direct3D runtime has transformed the vertex data.


### -field pfnDrawIndexedPrimitive2

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive2.md">DrawIndexedPrimitive2</a> function that draws indexed primitives in which the Direct3D runtime has transformed the vertex data.


### -field pfnVolBlt

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_volblt.md">VolBlt</a> function that performs a bit-block transfer (bitblt) from a source volume texture to a destination volume texture.


### -field pfnBufBlt

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_bufblt.md">BufBlt</a> function that performs a bitblt from a source vertex or index buffer to a destination vertex or index buffer.


### -field pfnTexBlt

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_texblt.md">TexBlt</a> function that performs a bitblt from a source texture to a destination texture.


### -field pfnStateSet

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_stateset.md">StateSet</a> function that performs a state-set operation.


### -field pfnSetPriority

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpriority.md">SetPriority</a> function that sets the eviction-from-memory priority for a managed texture.


### -field pfnClear

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_clear.md">Clear</a> function that performs hardware-assisted clearing on the rendering target, depth buffer, or stencil buffer.


### -field pfnUpdatePalette

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updatepalette.md">UpdatePalette</a> function that updates a texture palette.


### -field pfnSetPalette

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpalette.md">SetPalette</a> function that sets the palette for a texture.


### -field pfnSetVertexShaderConst

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setvertexshaderconst.md">SetVertexShaderConst</a> function that sets one or more vertex shader constant registers with float values.


### -field pfnMultiplyTransform

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_multiplytransform.md">MultiplyTransform</a> function that multiplies a current transform.


### -field pfnSetTransform

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_settransform.md">SetTransform</a> function that sets up a transform.


### -field pfnSetViewport

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setviewport.md">SetViewport</a> function that informs guard-band aware drivers of the view-clipping rectangle.


### -field pfnSetZRange

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setzrange.md">SetZRange</a> function that informs the driver about the range of z values.


### -field pfnSetMaterial

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmaterial.md">SetMaterial</a> function that sets the material properties that devices on the system use to create the required effect during rendering.


### -field pfnSetLight

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setlight.md">SetLight</a> function that sets properties for a light source.


### -field pfnCreateLight

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createlight.md">CreateLight</a> function that creates a light source.


### -field pfnDestroyLight

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroylight.md">DestroyLight</a> function that deactivates a light source.


### -field pfnSetClipPlane

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setclipplane.md">SetClipPlane</a> function that sets a clip plane.


### -field pfnGetInfo

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getinfo.md">GetInfo</a> function that retrieves information about the device.


### -field pfnLock

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a> function that locks a resource or a surface within the resource.


### -field pfnUnlock

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock.md">Unlock</a> function that unlocks a resource or a surface within the resource that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a> function previously locked.


### -field pfnCreateResource

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function that creates a resource.


### -field pfnDestroyResource

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyresource.md">DestroyResource</a> function that releases the resource that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function created.


### -field pfnSetDisplayMode

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymode.md">SetDisplayMode</a> function that sets a surface for displaying.


### -field pfnPresent

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a> function that requests that the source surface be displayed by either copying or flipping. 


### -field pfnFlush

A pointer to the user-mode display driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush.md">Flush</a> function that submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver.


### -field pfnCreateVertexShaderFunc

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderfunc.md">CreateVertexShaderFunc</a> function that converts the vertex shader code into a hardware-specific format and associates this code with the given shader handle.


### -field pfnDeleteVertexShaderFunc

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deletevertexshaderfunc.md">DeleteVertexShaderFunc</a> function that cleans up driver-side resources that are associated with vertex shader code.


### -field pfnSetVertexShaderFunc

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setvertexshaderfunc.md">SetVertexShaderFunc</a> function that sets the vertex shader code so that all of the subsequent drawing operations use that code.


### -field pfnCreateVertexShaderDecl

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderdecl.md">CreateVertexShaderDecl</a> function that converts the vertex shader declaration into a hardware-specific format and associates this declaration with the given shader handle.


### -field pfnDeleteVertexShaderDecl

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deletevertexshaderdecl.md">DeleteVertexShaderDecl</a> function that cleans up driver-side resources that are associated with the vertex shader declaration.


### -field pfnSetVertexShaderDecl

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setvertexshaderdecl.md">SetVertexShaderDecl</a> function that sets the vertex shader declaration so that all of the subsequent drawing operations use that declaration.


### -field pfnSetVertexShaderConstI

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setvertexshaderconst.md">SetVertexShaderConstI</a> function that sets one or more vertex shader constant registers with integer values.


### -field pfnSetVertexShaderConstB

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setvertexshaderconstb.md">SetVertexShaderConstB</a> function that sets one or more vertex shader constant registers with Boolean values.


### -field pfnSetScissorRect

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setscissorrect.md">SetScissorRect</a> function that marks a portion of a render target to which rendering is restricted.


### -field pfnSetStreamSource

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setstreamsource.md">SetStreamSource</a> function that binds a portion of a vertex stream source to a vertex buffer.


### -field pfnSetStreamSourceFreq

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setstreamsourcefreq.md">SetStreamSourceFreq</a> function that sets the frequency divisor of a stream source that is bound to a vertex buffer.


### -field pfnSetConvolutionKernelMono

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setconvolutionkernelmono.md">SetConvolutionKernelMono</a> function that sets the monochrome convolution kernel.


### -field pfnComposeRects

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_composerects.md">ComposeRects</a> function that composes rectangular areas.


### -field pfnBlt

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_blt.md">Blt</a> function that copies the contents of a source surface to a destination surface.


### -field pfnColorFill

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_colorfill.md">ColorFill</a> function that fills a rectangular area on a surface with a particular A8R8G8B8 color.


### -field pfnDepthFill

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_depthfill.md">DepthFill</a> function that fills a depth buffer with a pixel value that is specified in native format.


### -field pfnCreateQuery

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a> function that creates driver-side resources for a query that the Direct3D runtime subsequently issues for processing.


### -field pfnDestroyQuery

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyquery.md">DestroyQuery</a> function that releases resources for the query that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a> function created.


### -field pfnIssueQuery

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_issuequery.md">IssueQuery</a> function that processes the query that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a> function created.


### -field pfnGetQueryData

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getquerydata.md">GetQueryData</a> function that retrieves information about a query.


### -field pfnSetRenderTarget

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setrendertarget.md">SetRenderTarget</a> function that sets the render target surface in the driver's context.


### -field pfnSetDepthStencil

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdepthstencil.md">SetDepthStencil</a> function that sets the depth buffer in the driver's context.


### -field pfnGenerateMipSubLevels

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_generatemipsublevels.md">GenerateMipSubLevels</a> function that regenerates the sublevels of a MIP-map texture.


### -field pfnSetPixelShaderConstI

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconsti.md">SetPixelShaderConstI</a> function that sets one or more pixel shader constant registers with integer values.


### -field pfnSetPixelShaderConstB

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpixelshaderconstb.md">SetPixelShaderConstB</a> function that sets one or more pixel shader constant registers with Boolean values.


### -field pfnCreatePixelShader

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createpixelshader.md">CreatePixelShader</a> function that converts the pixel shader code into a hardware-specific format and associates this code with a shader handle.


### -field pfnDeletePixelShader

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deletepixelshader.md">DeletePixelShader</a> function that cleans up driver-side resources that are associated with pixel shader code.


### -field pfnCreateDecodeDevice

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a> function that creates a representation of a Microsoft DirectX Video Acceleration (VA) decode device from supplied parameters.


### -field pfnDestroyDecodeDevice

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroydecodedevice.md">DestroyDecodeDevice</a> function that releases resources for a DirectX VA decode device.


### -field pfnSetDecodeRenderTarget

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdecoderendertarget.md">SetDecodeRenderTarget</a> function that sets the render target for decoding. <i>SetDecodeRenderTarget</i> can be called only outside of a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>/<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeendframe.md">DecodeEndFrame</a> block.


### -field pfnDecodeBeginFrame

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a> function that indicates that decoding of a frame can begin.


### -field pfnDecodeEndFrame

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeendframe.md">DecodeEndFrame</a> function that indicates that frame decoding operations must be completed.


### -field pfnDecodeExecute

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeexecute.md">DecodeExecute</a> function that performs a DirectX VA decode operation. <i>DecodeExecute</i> must be called inside a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>/<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeendframe.md">DecodeEndFrame</a> block.


### -field pfnDecodeExtensionExecute

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeextensionexecute.md">DecodeExtensionExecute</a> function that performs a nonstandard DirectX VA decode operation. <i>DecodeExtensionExecute</i> must be called inside a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>/<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeendframe.md">DecodeEndFrame</a> block.


### -field pfnCreateVideoProcessDevice

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a> function that creates a representation of a DirectX VA video processing device from supplied parameters.


### -field pfnDestroyVideoProcessDevice

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyvideoprocessdevice.md">DestroyVideoProcessDevice</a> function that releases resources for a DirectX VA video processing device.


### -field pfnVideoProcessBeginFrame

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessbeginframe.md">VideoProcessBeginFrame</a> function that indicates that video processing of a frame can begin.


### -field pfnVideoProcessEndFrame

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessendframe.md">VideoProcessEndFrame</a> function that indicates that video processing operations must be completed.


### -field pfnSetVideoProcessRenderTarget

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setvideoprocessrendertarget.md">SetVideoProcessRenderTarget</a> function that sets the render target for video processing. <i>SetVideoProcessRenderTarget</i> can be called only outside of a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessbeginframe.md">VideoProcessBeginFrame</a>/<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessendframe.md">VideoProcessEndFrame</a> block.


### -field pfnVideoProcessBlt

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessblt.md">VideoProcessBlt</a> function that processes DirectX VA video. <i>VideoProcessBlt</i> must be called inside a <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessbeginframe.md">VideoProcessBeginFrame</a>/<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessendframe.md">VideoProcessEndFrame</a> block.


### -field pfnCreateExtensionDevice

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createextensiondevice.md">CreateExtensionDevice</a> function that creates a representation of a DirectX VA extension device from supplied parameters.


### -field pfnDestroyExtensionDevice

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyextensiondevice.md">DestroyExtensionDevice</a> function that releases resources for a DirectX VA extension device.


### -field pfnExtensionExecute

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_extensionexecute.md">ExtensionExecute</a> function that performs an operation that is specific to the given DirectX VA extension device.


### -field pfnCreateOverlay

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlay.md">CreateOverlay</a> function that allocates overlay hardware and makes the overlay visible.


### -field pfnUpdateOverlay

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlay.md">UpdateOverlay</a> function that reconfigures or moves an overlay that is being displayed.


### -field pfnFlipOverlay

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlay.md">FlipOverlay</a> function that causes the overlay hardware to start displaying the new allocation.


### -field pfnGetOverlayColorControls

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getoverlaycolorcontrols.md">GetOverlayColorControls</a> function that retrieves color-control settings for an overlay.


### -field pfnSetOverlayColorControls

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setoverlaycolorcontrols.md">SetOverlayColorControls</a> function that changes color-control settings for an overlay.


### -field pfnDestroyOverlay

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlay.md">DestroyOverlay</a> function that disables the overlay hardware and frees the overlay handle.


### -field pfnDestroyDevice

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroydevice.md">DestroyDevice</a> function that releases resources for the display device.


### -field pfnQueryResourceResidency

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresourceresidency.md">QueryResourceResidency</a> function that determines the residency of resources.


### -field pfnOpenResource

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openresource.md">OpenResource</a> function that informs the driver that a shared resource is opened.


### -field pfnGetCaptureAllocationHandle

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaptureallocationhandle.md">GetCaptureAllocationHandle</a> function that maps the given capture resource to an allocation.


### -field pfnCaptureToSysMem

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_capturetosysmem.md">CaptureToSysMem</a> function that copies a capture buffer to a video memory surface.


### -field pfnLockAsync

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function that locks a resource or a surface within the resource.


### -field pfnUnlockAsync

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockasync.md">UnlockAsync</a> function that unlocks a resource or a surface within the resource that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function previously locked.


### -field pfnRename

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rename.md">Rename</a> function that renames, with a new allocation, a resource or a surface within the resource.


### -field pfnCreateVideoProcessor

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor.md">CreateVideoProcessor</a> function that creates a video processor.


### -field pfnSetVideoProcessBltState

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a> function that sets the state of a bitblt for a video processor. 


### -field pfnGetVideoProcessBltStatePrivate

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessbltstateprivate.md">GetVideoProcessBltStatePrivate</a> function that retrieves the state data of a private bitblt for a video processor. 


### -field pfnSetVideoProcessStreamState

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a> function that sets the state of a stream for a video processor. 


### -field pfnGetVideoProcessStreamStatePrivate

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate.md">GetVideoProcessStreamStatePrivate</a> function that retrieves the private stream-state data for a video processor. 


### -field pfnVideoProcessBltHD

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd.md">VideoProcessBltHD</a> function that processes video input streams and composes to an output surface. 


### -field pfnDestroyVideoProcessor

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_destroyvideoprocessor.md">DestroyVideoProcessor</a> function that releases resources for a previously created video processor. 


### -field pfnCreateAuthenticatedChannel

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createauthenticatedchannel.md">CreateAuthenticatedChannel</a> function that creates a channel that the Direct3D runtime and the driver can use to set and query protections. 


### -field pfnAuthenticatedChannelKeyExchange

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_authenticatedchannelkeyexchange.md">AuthenticatedChannelKeyExchange</a> function that negotiates the session key. 


### -field pfnQueryAuthenticatedChannel

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel</a> function that queries an authenticated channel for capability and state information. 


### -field pfnConfigureAuthenticatedChannel

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> function that sets the state within an authenticated channel. 


### -field pfnDestroyAuthenticatedChannel

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyauthenticatedchannel.md">DestroyAuthenticatedChannel</a> function that releases resources for an authenticated channel. 


### -field pfnCreateCryptoSession

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function that creates an encryption session. 


### -field pfnCryptoSessionKeyExchange

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_cryptosessionkeyexchange.md">CryptoSessionKeyExchange</a> function that performs a key exchange during an encryption session. 


### -field pfnDestroyCryptoSession

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycryptosession.md">DestroyCryptoSession</a> function that releases resources for an encryption session. 


### -field pfnEncryptionBlt

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_encryptionblt.md">EncryptionBlt</a> function that performs an encrypted bitblt operation. 


### -field pfnGetPitch

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getpitch.md">GetPitch</a> function that retrieves the pitch of an encrypted surface. 


### -field pfnStartSessionKeyRefresh

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_startsessionkeyrefresh.md">StartSessionKeyRefresh</a> function that sets the current video session to protected mode. 


### -field pfnFinishSessionKeyRefresh

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a> function that sets the current video session to unprotected mode. 


### -field pfnGetEncryptionBltKey

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getencryptionbltkey.md">GetEncryptionBltKey</a> function that retrieves the key of an encrypted bitblt session. 


### -field pfnDecryptionBlt

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a> function that writes data to a protected surface. 


### -field pfnResolveSharedResource

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_resolvesharedresource.md">ResolveSharedResource</a> function that resolves a shared resource. 


### -field pfnVolBlt1

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_volblt1.md">VolBlt1</a> function that performs a volume bit-block transfer (bitblt) operation.

Supported starting with Windows 8.


### -field pfnBufBlt1

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_bufblt1.md">BufBlt1</a> function that performs a bit-block transfer (bitblt) operation.

Supported starting with Windows 8.


### -field pfnTexBlt1

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_texblt1.md">TexBlt1</a> function that performs a texture bit-block transfer (bitblt) operation.

Supported starting with Windows 8.


### -field pfnDiscard

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_discard.md">Discard</a>  function that discards (evicts) a set of subresources from video display memory.

Supported starting with Windows 8.


### -field pfnOfferResources

A pointer to the driver  <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerresources.md">OfferResources</a> function that requests that the user-mode display driver offer video memory resources for reuse.

Supported starting with Windows 8.


### -field pfnReclaimResources

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimresources.md">ReclaimResources</a> function that's called by the Direct3D runtime to reclaim video memory resources that it previously offered for reuse.

Supported starting with Windows 8.


### -field pfnCheckDirectFlipSupport

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkdirectflipsupport.md">CheckDirectFlipSupport</a> function that's called by the DWM to verify that the user-mode driver supports Direct Flip operations.

Supported starting with Windows 8.


### -field pfnCreateResource2

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource2.md">CreateResource2</a> function that creates a resource.

Supported starting with Windows 8.


### -field pfnCheckMultiPlaneOverlaySupport

A pointer to the driver <a href="https://msdn.microsoft.com/A439E695-D374-439A-8A69-6D4E247FF134">pfnCheckMultiPlaneOverlaySupport (D3D)</a> function that's called by the Direct3D runtime to check the details on hardware support for multiplane overlays.

Supported starting with Windows 8.1.


### -field pfnPresentMultiPlaneOverlay

A pointer to the driver <a href="https://msdn.microsoft.com/3AC47977-A5F3-44A6-8F89-A1EA5E0BB6E4">pfnPresentMultiplaneOverlay (D3D)</a> function that's called by the Direct3D runtime to notify the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation.

Supported starting with Windows 8.1.


### -field pfnReserved1

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.1.


### -field pfnFlush1

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush1.md">pfnFlush1</a>  function that's called by the Direct3D runtime to submit outstanding hardware commands that are in the hardware command buffer to the display miniport driver.

Supported starting with Windows 8.1.


### -field pfnCheckCounterInfo

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkcounterinfo.md">pfnCheckCounterInfo</a>  function that's called by the Direct3D runtime to determine global information that's related to manipulating counters.

Supported starting with Windows 8.1.


### -field pfnCheckCounter

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkcounter.md">pfnCheckCounter</a>  function that's called by the Direct3D runtime to retrieve info that describes a counter.

Supported starting with Windows 8.1.


### -field pfnUpdateSubresourceUP

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updatesubresourceup.md">pfnUpdateSubresourceUP</a>  function that's called by the Direct3D runtime to update a destination subresource region from a source system-memory region.

Supported starting with Windows 8.1.


### -field pfnPresent1

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present1.md">pfnPresent1(D3D)</a>  function that notifies the user-mode display driver that an application finished rendering and  that all ownership of the shared resource is released, and that  requests that the driver display to the destination surface.

Supported starting with Windows 8.1.


### -field pfnCheckPresentDurationSupport

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkpresentdurationsupport.md">CheckPresentDurationSupport</a> function that's called by the Direct3D runtime to request that the user-mode display driver get hardware device capabilities for seamlessly switching to a new monitor refresh rate.

Supported starting with Windows 8.1.


### -field pfnSetMarker

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmarker.md">pfnSetMarker</a> function that notifies the user-mode display driver that it must generate a new time stamp if any GPU work has completed since the last call to <i>pfnSetMarker</i>.

Supported starting with Windows 8.1.


### -field pfnSetMarkerMode

A pointer to the driver <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmarkermode.md">pfnSetMarkerMode</a> function that notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event.

Supported starting with Windows 8.1.


### -field pfnTrimResidencySet

 


### -field pfnAcquireResource

 


### -field pfnReleaseResource

 




## -remarks



The following code, from D3dumddi.h, shows the function declarations for the functions that the members of <b>D3DDDI_DEVICEFUNCS</b> point to. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETRENDERSTATE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_RENDERSTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UPDATEWINFO)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_WINFO*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VALIDATEDEVICE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_VALIDATETEXTURESTAGESTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETTEXTURESTAGESTATE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_TEXTURESTAGESTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETTEXTURE)(
        _In_ HANDLE hDevice, _In_ UINT, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPIXELSHADER)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPIXELSHADERCONST)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPIXELSHADERCONST*, _In_ CONST FLOAT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETSTREAMSOURCEUM)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETSTREAMSOURCEUM*, _In_ CONST VOID*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETINDICES)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETINDICES*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETINDICESUM)(
        _In_ HANDLE hDevice, _In_ UINT, _In_ CONST VOID*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWPRIMITIVE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWPRIMITIVE*, _In_opt_ CONST UINT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWINDEXEDPRIMITIVE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWINDEXEDPRIMITIVE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWRECTPATCH)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWRECTPATCH*, _In_ CONST D3DDDIRECTPATCH_INFO*, _In_ CONST FLOAT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWTRIPATCH)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWTRIPATCH*, _In_ CONST D3DDDITRIPATCH_INFO*, _In_ CONST FLOAT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWPRIMITIVE2)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWPRIMITIVE2*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DRAWINDEXEDPRIMITIVE2)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DRAWINDEXEDPRIMITIVE2*, _In_ UINT, _In_ CONST VOID*, _In_opt_ CONST UINT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VOLBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_VOLUMEBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_BUFBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_BUFFERBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_TEXBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_TEXBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_STATESET)(
        _In_ HANDLE hDevice, _In_ D3DDDIARG_STATESET*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPRIORITY)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPRIORITY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CLEAR)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_CLEAR*, _In_ UINT, _In_ CONST RECT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UPDATEPALETTE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UPDATEPALETTE*, _In_ CONST PALETTEENTRY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPALETTE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPALETTE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERCONST)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETVERTEXSHADERCONST*, _In_ CONST VOID*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_MULTIPLYTRANSFORM)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_MULTIPLYTRANSFORM*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETTRANSFORM)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETTRANSFORM*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVIEWPORT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_VIEWPORTINFO*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETZRANGE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_ZRANGE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETMATERIAL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETMATERIAL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETLIGHT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETLIGHT*, _In_ CONST D3DDDI_LIGHT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATELIGHT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_CREATELIGHT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYLIGHT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DESTROYLIGHT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETCLIPPLANE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETCLIPPLANE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETINFO)(
        _In_ HANDLE hDevice, _In_ UINT, _Out_writes_bytes_(DevInfoSize)VOID*, _In_ UINT DevInfoSize);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_LOCK)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_LOCK*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UNLOCK)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UNLOCK*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_LOCKASYNC)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_LOCKASYNC*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UNLOCKASYNC)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UNLOCKASYNC*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_RENAME)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_RENAME*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATERESOURCE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATERESOURCE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYRESOURCE)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETDISPLAYMODE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETDISPLAYMODE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_PRESENT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_PRESENT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_FLUSH)(
        _In_ HANDLE hDevice);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEVERTEXSHADERDECL)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEVERTEXSHADERDECL*, _In_ CONST D3DDDIVERTEXELEMENT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERDECL)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DELETEVERTEXSHADERDECL)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEVERTEXSHADERFUNC)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEVERTEXSHADERFUNC*, _In_ CONST UINT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERFUNC)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _In_ HRESULT (APIENTRY *PFND3DDDI_DELETEVERTEXSHADERFUNC)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERCONSTI)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETVERTEXSHADERCONSTI*, _In_ CONST INT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVERTEXSHADERCONSTB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETVERTEXSHADERCONSTB*, _In_ CONST BOOL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETSCISSORRECT)(
        _In_ HANDLE hDevice, _In_ CONST RECT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETSTREAMSOURCE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETSTREAMSOURCE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETSTREAMSOURCEFREQ)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETSTREAMSOURCEFREQ*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETCONVOLUTIONKERNELMONO)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETCONVOLUTIONKERNELMONO*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_COMPOSERECTS)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_COMPOSERECTS*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_BLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_BLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_COLORFILL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_COLORFILL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DEPTHFILL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DEPTHFILL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEQUERY)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEQUERY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYQUERY)(
        _In_ HANDLE hDevice, _In_ CONST HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_ISSUEQUERY)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_ISSUEQUERY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETQUERYDATA)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_GETQUERYDATA*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETRENDERTARGET)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETRENDERTARGET*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETDEPTHSTENCIL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETDEPTHSTENCIL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GENERATEMIPSUBLEVELS)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_GENERATEMIPSUBLEVELS*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPIXELSHADERCONSTI)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPIXELSHADERCONSTI*, _In_ CONST INT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETPIXELSHADERCONSTB)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETPIXELSHADERCONSTB*, _In_ CONST BOOL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEPIXELSHADER)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEPIXELSHADER*, _In_ CONST UINT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DELETEPIXELSHADER)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEDECODEDEVICE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEDECODEDEVICE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYDECODEDEVICE)(
        _In_ HANDLE hDevice, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETDECODERENDERTARGET) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETDECODERENDERTARGET*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECODEBEGINFRAME) (
        _In_ HANDLE hDevice, _In_ D3DDDIARG_DECODEBEGINFRAME*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECODEENDFRAME) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_DECODEENDFRAME*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECODEEXECUTE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DECODEEXECUTE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECODEEXTENSIONEXECUTE)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_DECODEEXTENSIONEXECUTE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEVIDEOPROCESSDEVICE) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEVIDEOPROCESSDEVICE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYVIDEOPROCESSDEVICE) (
        _In_ HANDLE hDevice, _In_ HANDLE hVideoProcessor);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VIDEOPROCESSBEGINFRAME) (
        _In_ HANDLE hDevice, _In_ HANDLE hVideoProcess);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VIDEOPROCESSENDFRAME) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_VIDEOPROCESSENDFRAME*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETVIDEOPROCESSRENDERTARGET) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETVIDEOPROCESSRENDERTARGET*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VIDEOPROCESSBLT) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_VIDEOPROCESSBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEEXTENSIONDEVICE) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEEXTENSIONDEVICE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYEXTENSIONDEVICE) (
        _In_ HANDLE hDevice, _In_ HANDLE hExtension);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_EXTENSIONEXECUTE) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_EXTENSIONEXECUTE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYDEVICE)(
        _In_ HANDLE hDevice);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEOVERLAY) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UPDATEOVERLAY) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UPDATEOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_FLIPOVERLAY) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_FLIPOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETOVERLAYCOLORCONTROLS) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_GETOVERLAYCOLORCONTROLS*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETOVERLAYCOLORCONTROLS) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_SETOVERLAYCOLORCONTROLS*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYOVERLAY) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DESTROYOVERLAY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_QUERYRESOURCERESIDENCY) (
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_QUERYRESOURCERESIDENCY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_OPENRESOURCE) (
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_OPENRESOURCE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETCAPTUREALLOCATIONHANDLE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_GETCAPTUREALLOCATIONHANDLE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CAPTURETOSYSMEM)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_CAPTURETOSYSMEM*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR)(
        _In_ HANDLE, _Inout_ D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_SETVIDEOPROCESSBLTSTATE)(
        _In_ HANDLE, _In_ CONST D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE)(
        _In_ HANDLE, _Inout_ D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE)(
        _In_ HANDLE, _In_ CONST D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE)(
        _In_ HANDLE, _Inout_ D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD)(
        _In_ HANDLE, _In_ CONST D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR)(
        _In_ HANDLE, _In_ HANDLE);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATEAUTHENTICATEDCHANNEL)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATEAUTHENTICATEDCHANNEL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_QUERYAUTHENTICATEDCHANNEL)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_QUERYAUTHENTICATEDCHANNEL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CONFIGUREAUTHENICATEDCHANNEL)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATECRYPTOSESSION)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATECRYPTOSESSION*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DESTROYCRYPTOSESSION)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DESTROYCRYPTOSESSION*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_ENCRYPTIONBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_ENCRYPTIONBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETPITCH)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_GETPITCH*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_STARTSESSIONKEYREFRESH)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_STARTSESSIONKEYREFRESH*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_FINISHSESSIONKEYREFRESH)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_FINISHSESSIONKEYREFRESH*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_GETENCRYPTIONBLTKEY)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_GETENCRYPTIONBLTKEY*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DECRYPTIONBLT)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DECRYPTIONBLT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_RESOLVESHAREDRESOURCE)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_RESOLVESHAREDRESOURCE*);
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WIN8)
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_VOLBLT1)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_VOLUMEBLT1*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_BUFBLT1)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_BUFFERBLT1*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_TEXBLT1)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_TEXBLT1*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_DISCARD)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_DISCARD*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_OFFERRESOURCES)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_OFFERRESOURCES*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_RECLAIMRESOURCES)(
        _In_ HANDLE hDevice, _Inout_ CONST D3DDDIARG_RECLAIMRESOURCES*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CHECKDIRECTFLIPSUPPORT)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CHECKDIRECTFLIPSUPPORT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CREATERESOURCE2)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CREATERESOURCE2*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT)(
        _In_ HANDLE hDevice, _Inout_ D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_PRESENTMULTIPLANEOVERLAY)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_PRESENTMULTIPLANEOVERLAY*);
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_FLUSH1)(
        _In_ HANDLE hDevice, UINT /*D3DDDI_FLUSH_FLAGS*/ FlushFlags);
typedef VOID ( APIENTRY* PFND3DDDI_CHECKCOUNTERINFO )(
        _In_ HANDLE hDevice, _Out_ D3DDDIARG_COUNTER_INFO* );
typedef _Check_return_ HRESULT ( APIENTRY* PFND3DDDI_CHECKCOUNTER )(
        _In_ HANDLE hDevice, _In_ D3DDDIQUERYTYPE, _Out_ D3DDDI_COUNTER_TYPE*, _Out_ UINT*,
        _Out_writes_to_opt_(*pNameLength, *pNameLength) LPSTR,
        _Inout_opt_ UINT* pNameLength,
        _Out_writes_to_opt_(*pUnitsLength, *pUnitsLength) LPSTR,
        _Inout_opt_ UINT* pUnitsLength,
        _Out_writes_to_opt_(*pDescriptionLength, *pDescriptionLength) LPSTR,
        _Inout_opt_ UINT* pDescriptionLength);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_UPDATESUBRESOURCEUP)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_UPDATESUBRESOURCEUP*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_PRESENT1)(
        _In_ HANDLE hDevice, _In_ CONST D3DDDIARG_PRESENT1*);
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_CHECKPRESENTDURATIONSUPPORT)(
        _In_ HANDLE hDevice, _In_ D3DDDIARG_CHECKPRESENTDURATIONSUPPORT*);
#endif // D3D_UMD_INTERFACE_VERSION
#if (D3D_UMD_INTERFACE_VERSION &gt;= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETMARKERMODE)(
        _In_ HANDLE hDevice, _In_ D3DDDI_MARKERTYPE Type, /*D3DDDI_SETMARKERMODE*/ UINT Flags );
typedef _Check_return_ HRESULT (APIENTRY *PFND3DDDI_SETMARKER)(
        _In_ HANDLE hDevice);
#endif // D3D_UMD_INTERFACE_VERSION</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_DEVICEFUNCS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

