# RENCORE’S CUSTOMIZATION GUIDE

The following guide is meant to bring clarity to customizing SharePoint and help you choose technologies that you can safely rely on for the foreseeable future. The intent is to provide our best recommendations regarding current and upcoming customizing practices and to provide some additional insight in our recommendations.

> **Disclaimer:** This page is based on our experience in customizing SharePoint and we provide no guarantee to its completeness or accuracy.

Last Update: July 12th, 2017

## Avoid

Customization capability|Status|Comments
------------------------|------|--------
Ribbon customization via User Custom Actions|Avoid|There is no Ribbon in the modern UI. Ribbon customizations are not upgradeable and need to be redone from scratch for the modern UI.
Customization through DOM manipulation|Avoid|Not supported in the modern UI. Unreliable as the DOM in SharePoint Online is prone to frequent changes.
Custom Master Pages|Avoid|Not supported in the modern UI. Customization is not upgradeable and will likely need to be redone for the modern UI.
Custom Page Layouts|Avoid|Not supported in the modern UI. Customization is not upgradeable and will likely need to be redone for the modern UI.
Content/Script Editor Web Part-based solutions|Avoid|Hard to govern and manage centrally. Not available in modern UI. Use SharePoint Framework client-side web parts instead.
Customizing list forms|Avoid|Not supported in the modern UI. Blocks you from using the modern UI. Use client-side applications or Microsoft PowerApps instead
Adding web parts to list form pages|Avoid|Not supported in the modern UI. Blocks you from using the modern UI. Use client-side applications or Microsoft PowerApps instead.
Custom List Templates (Save List as Template)|Avoid|Impossible to manage. List instances tied to the original list and break when the original list is deleted. Consider using remote provisioning instead.
Custom List Definitions|Avoid|Rely on declarative provisioning. List instances tied to the list definition and break when the feature is removed. Consider using remote provisioning instead.
Custom Site Templates|Avoid|Rely on declarative provisioning that should be avoided. Consider using PnP provisioning engine and its templates instead.
Sandboxed Solutions with code|Avoid|Deprecated, not supported anymore.
SharePoint Designer Workflows|Avoid|Deprecated, use Microsoft Flow or 3rd party solutions instead.
InfoPath Forms|Avoid|Deprecated, use Microsoft PowerApps or 3rd party solutions instead.
SharePoint-hosted add-ins|Avoid|Limited functionality, consider using SharePoint Framework client-side web parts or provider-hosted add-ins if you need isolation or full-page applications.
Design Packages|Avoid|Rely on no-code Sandboxed Solutions, declarative provisioning and custom Master Pages all of which should be avoided.
Access applications|Avoid|Deprecated. Consider using Microsoft PowerApps instead.
Declarative provisioning via no-code Sandboxed Solutions|Avoid|Based on declarative provisioning which should be avoided due to its limitations. Use remote provisioning instead.
JavaScript Object Model|Avoid|Limited and not invested in anymore. Consider using REST or SP PnP JS Core instead

## Caution

Customization capability|Status|Comments
------------------------|------|--------
JS Link|Caution|While not upgradeable to the modern UI, JS Link is the only way to customize fields for the classic UI. For full support of both the classic and the modern UI needs to be complimented by SharePoint Framework extensions which are currently in developer preview.
Script injection via User Custom Actions|Caution|Required to customize the classic UI. Avoid DOM manipulation as its error-prone and not supported in the modern UI.
Display Templates|Caution|Necessary to customize the classic SharePoint Search results but not upgradeable to the modern UI. Will likely need to be redone from scratch for the modern UI.
Content Query Web Part-based solutions|Caution|Limited to a single site collection but often required when you cant wait on new content to be crawled by search. If search latency is not an issue, consider using Content Search Web Part instead  which is more powerful.
Content Search Web Part-based solutions|Caution|Not available in the modern UI. Customization will likely need to be redone from scratch for the modern UI.
Search Query Web Part-based solutions|Caution|Not available in the modern UI. Customization will likely need to be redone from scratch for the modern UI.
Content Type Hub|Caution|Often required for ECM scenarios but beware of timing issues when creating new sites. Content Types are also not added to new document libraries. Consider using remote provisioning instead.
Microsoft PowerApps|Caution|Early technology. Research its limitations before relying on it for your solution.
Microsoft Flow|Caution|Early technology. Research its limitations before relying on it for your solution.
SharePoint Framework extensions|Caution|Developer preview only, not supported in production yet. Research for applicability but don't use in production just yet.
Publishing Sites|Caution|The only way to implement publishing in SharePoint but at the moment has unclear future regarding how publishing will look like on top of the SharePoint Framework and to what extent current customization efforts will be upgradeable.

## Do

Customization capability|Status|Comments
------------------------|------|--------
Custom Content Types|Do|Required for ECM scenarios. Avoid declarative provisioning and use remote provisioning instead.
Custom Site Columns|Do|Required for ECM scenarios. Avoid declarative provisioning and use remote provisioning instead.
Single Page Applications hosted in SharePoint|Do|Still a reliable way of building applications for SharePoint Online. No alternative in the SharePoint Framework available at the moment.
Provider-hosted add-ins|Do|Still valid approach for building SharePoint solutions. Consider SharePoint Framework client-side web parts instead unless you require web part isolation.
SharePoint Framework client-side web parts|Do|Supported in both classic and modern UI. Actively developed and invested in.
Client-Side Object Model (CSOM)|Do|Simplifies communicating with SharePoint, actively managed. SLA-backed by Microsoft.
SP PnP JS Core|Do|Significantly simplifies communicating with SharePoint in client-side solutions. Keep in mind that it's a community-driven effort with no SLA behind it.
SP PnP Core|Do|Significantly simplifies communicating with SharePoint. Keep in mind that it's a community-driven effort with no SLA behind it.