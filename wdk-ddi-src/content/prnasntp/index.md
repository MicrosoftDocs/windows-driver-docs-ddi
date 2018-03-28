---
UID: NA:prnasntp
ms.assetid: 06a2babb-67c2-3b95-be24-a44b7eec0bcf
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Prnasntp.h header



This header is used by print. For more information, see
- [print](../_print/index.md)

Prnasntp.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [RouterCreatePrintAsyncNotificationChannel function](nf-prnasntp-routercreateprintasyncnotificationchannel.md) | The RouterCreatePrintAsyncNotificationChannel function creates an asynchronous notification channel that is associated with a printer or print server. |
| [RouterGetPrintClassObject function](nf-prnasntp-routergetprintclassobject.md) | The RouterGetPrintClassObject function enumerates the list of print providers, searching for the print provider with the specified name and interface ID. |
| [RouterRegisterForPrintAsyncNotifications function](nf-prnasntp-routerregisterforprintasyncnotifications.md) | The RouterRegisterForPrintAsyncNotifications function registers for asynchronous notifications associated with a printer or print server. |
| [RouterUnregisterForPrintAsyncNotifications function](nf-prnasntp-routerunregisterforprintasyncnotifications.md) | The RouterUnregisterForPrintAsyncNotifications function unregisters for receiving asynchronous notifications associated with a printer or print server. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IAsyncGetSendNotificationCookie interface](nn-prnasntp-iasyncgetsendnotificationcookie.md) | "." |
| [IAsyncGetSrvReferralCookie interface](nn-prnasntp-iasyncgetsrvreferralcookie.md) | "." |
| [IBidiAsyncNotifyChannel interface](nn-prnasntp-ibidiasyncnotifychannel.md) | "." |
| [IPrintAsyncCookie interface](nn-prnasntp-iprintasynccookie.md) | "." |
| [IPrintAsyncNewChannelCookie interface](nn-prnasntp-iprintasyncnewchannelcookie.md) | "." |
| [IPrintAsyncNotify interface](nn-prnasntp-iprintasyncnotify.md) | "." |
| [IPrintAsyncNotifyRegistration interface](nn-prnasntp-iprintasyncnotifyregistration.md) | "." |
| [IPrintAsyncNotifyServerReferral interface](nn-prnasntp-iprintasyncnotifyserverreferral.md) | "." |
| [IPrintBidiAsyncNotifyRegistration interface](nn-prnasntp-iprintbidiasyncnotifyregistration.md) | "." |
| [IPrintUnidiAsyncNotifyRegistration interface](nn-prnasntp-iprintunidiasyncnotifyregistration.md) | Provides information on IPrintUnidiAsyncNotifyRegistration constructs. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IBidiAsyncNotifyChannel::AsyncCloseChannel method](nf-prnasntp-ibidiasyncnotifychannel-asyncclosechannel.md) | "." |
| [IBidiAsyncNotifyChannel::AsyncGetNotificationSendResponse method](nf-prnasntp-ibidiasyncnotifychannel-asyncgetnotificationsendresponse.md) | "." |
| [IBidiAsyncNotifyChannel::CloseChannel method](nf-prnasntp-ibidiasyncnotifychannel-closechannel.md) | "." |
| [IBidiAsyncNotifyChannel::CreateNotificationChannel method](nf-prnasntp-ibidiasyncnotifychannel-createnotificationchannel.md) | "." |
| [IBidiAsyncNotifyChannel::GetChannelNotificationType method](nf-prnasntp-ibidiasyncnotifychannel-getchannelnotificationtype.md) | "." |
| [IBidiAsyncNotifyChannel::GetPrintName method](nf-prnasntp-ibidiasyncnotifychannel-getprintname.md) | "." |
| [IBidiAsyncNotifyChannel::SendNotification method](nf-prnasntp-ibidiasyncnotifychannel-sendnotification.md) | "." |
| [IPrintAsyncCookie::CancelAsyncCall method](nf-prnasntp-iprintasynccookie-cancelasynccall.md) | "." |
| [IPrintAsyncCookie::FinishAsyncCall method](nf-prnasntp-iprintasynccookie-finishasynccall.md) | "." |
| [IPrintAsyncNewChannelCookie::FinishAsyncCallWithData method](nf-prnasntp-iprintasyncnewchannelcookie-finishasynccallwithdata.md) | "." |
| [IPrintAsyncNotify::CreatePrintAsyncNotifyChannel method](nf-prnasntp-iprintasyncnotify-createprintasyncnotifychannel.md) | "." |
| [IPrintAsyncNotify::CreatePrintAsyncNotifyRegistration method](nf-prnasntp-iprintasyncnotify-createprintasyncnotifyregistration.md) | "." |
| [IPrintAsyncNotifyRegistration::RegisterForNotifications method](nf-prnasntp-iprintasyncnotifyregistration-registerfornotifications.md) | "." |
| [IPrintAsyncNotifyRegistration::UnregisterForNotifications method](nf-prnasntp-iprintasyncnotifyregistration-unregisterfornotifications.md) | "." |
| [IPrintAsyncNotifyServerReferral::AsyncGetServerReferral method](nf-prnasntp-iprintasyncnotifyserverreferral-asyncgetserverreferral.md) | "." |
| [IPrintAsyncNotifyServerReferral::GetServerReferral method](nf-prnasntp-iprintasyncnotifyserverreferral-getserverreferral.md) | "." |
| [IPrintAsyncNotifyServerReferral::SetServerReferral method](nf-prnasntp-iprintasyncnotifyserverreferral-setserverreferral.md) | "." |
| [IPrintBidiAsyncNotifyRegistration::AsyncGetNewChannel method](nf-prnasntp-iprintbidiasyncnotifyregistration-asyncgetnewchannel.md) | "." |
| [IPrintUnidiAsyncNotifyRegistration::AsyncGetNotification method](nf-prnasntp-iprintunidiasyncnotifyregistration-asyncgetnotification.md) | "." |
