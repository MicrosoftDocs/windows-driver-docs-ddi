---
UID: NF:wdfinstaller.WdfPreDeviceInstall
title: WdfPreDeviceInstall function (wdfinstaller.h)
description: The co-installer's WdfPreDeviceInstall function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service.
old-location: wdf\wdfpredeviceinstall.htm
tech.root: wdf
ms.assetid: 2da4b4ea-1cbb-43f7-9001-44b07a3e9ef7
ms.date: 02/26/2018
keywords: ["WdfPreDeviceInstall function"]
ms.keywords: DFCoinstallerRef_0d1aca8b-f318-42c4-a74d-bd69d272ceec.xml, WdfPreDeviceInstall, WdfPreDeviceInstall function, kmdf.wdfpredeviceinstall, wdf.wdfpredeviceinstall, wdfinstaller/WdfPreDeviceInstall
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see Using the KMDF Co-installer.)
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfPreDeviceInstall
 - wdfinstaller/WdfPreDeviceInstall
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - N/A
 - N/A.dll
api_name:
 - WdfPreDeviceInstall
---

# WdfPreDeviceInstall function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The co-installer's <b>WdfPreDeviceInstall</b> function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service.

## -parameters

### -param InfPath 

[in]
A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <a href="https://docs.microsoft.com/windows/win32/api/winbase/nf-winbase-getcurrentdirectory">GetCurrentDirectory</a>, which is described in the Microsoft Windows SDK.

### -param InfSectionName 

[in, optional]
A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/installing-the-framework-s-co-installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.

## -returns

<b>WdfPreDeviceInstall</b> returns <b>ERROR_SUCCESS</b> if the operation succeeds. Otherwise, the function returns one of the additional <b>ERROR_XXX</b> values that are defined in Winerror.h.

## -remarks

The installer for the framework-based drivers of a non-PnP device must call <b>WdfPreDeviceInstall</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinstaller/nf-wdfinstaller-wdfpredeviceinstallex">WdfPreDeviceInstallEx</a> before the installer calls <a href="https://docs.microsoft.com/windows/win32/api/winsvc/nf-winsvc-createservicea">CreateService</a>.

To obtain the address of the co-installer's <b>WdfPreDeviceInstall</b> function, the installer must call <a href="https://docs.microsoft.com/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress">GetProcAddress</a> after the installer has called <a href="https://docs.microsoft.com/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibrarya">LoadLibrary</a> to load the co-installer.

If the co-installer determines that the computer must be restarted to complete the driver installation (typically because an older version of the framework was previously installed), <b>WdfPreDeviceInstall</b> informs the Plug and Play (PnP) manager. The PnP manager then prompts the user that a restart is necessary. 

For more information about the <b>WdfPreDeviceInstall</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/installing-a-non-pnp-driver">Installing a Non-PnP Driver</a>. For more information about <a href="https://docs.microsoft.com/windows/win32/api/winsvc/nf-winsvc-createservicea">CreateService</a>, <a href="https://docs.microsoft.com/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress">GetProcAddress</a>, and <a href="https://docs.microsoft.com/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibrarya">LoadLibrary</a>, see the Microsoft Windows SDK documentation.


#### Examples

For a code example that uses the <b>WdfPreDeviceInstall</b> function, see the installer for the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">NONPNP</a> sample.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinstaller/nf-wdfinstaller-wdfpostdeviceinstall">WdfPostDeviceInstall</a>

