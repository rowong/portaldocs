* [Onboarding](#onboarding)
    * [Portal extension](#onboarding-portal-extension)


 <h1 name="portalfx-extension-onboarding"></h1>
 
<a name="onboarding"></a>
# Onboarding
 <h1 name="portalfx-onboarding"></h1>
 Welcome to the Azure portal! We're excited to have you to join the family.

Most services consist of 3 components:

* Marketing content on [azure.com](https://azure.microsoft.com) or other website
* Management APIs exposed via Azure Resource Manager (ARM) or Microsoft Graph
* Management UI in the Azure portal and/or other tools/websites, like Visual Studio

The Azure onboarding process is streamlined to optimize the delivery of high quality experiences based on hundreds of
hours of usability testing that meet Microsoft Common Engineering Criteria (CEC) and compliance requirements. **Do not
start designing UI or management APIs until after you've started the onboarding process** to ensure you're following the
latest patterns and practices. This will better optimize your time and avoid throw-away work by avoiding usability
issues caused by anti-patterns and inconsistencies that block usability, performance, etc.

1. **Onboarding kickoff** (Stakeholders: [Leon Welicki, Adam Abdelhamed](mailto:ibiza-onboading-kick@microsoft.com?subject=Azure%20portal%20onboarding))

    Setup a meeting to discuss the following:
    - Is your service targeting public Azure, on-prem, or both?
    - Service name
    - VP, PM, and engineering owners
    - Timelines (preview, GA)
    - Summary of the service and target scenarios

2. **Business model review** (Stakeholders: [Brian Hillger’s team, Stacey Ellingson](mailto:ibiza-bmr@microsoft.com?subject=Azure%20Business%20model%20review)

3. **Management APIs in ARM/Graph**

    All services using Azure Billing must be exposed via Azure Resource Manager (ARM), the replacement for RDFE (Red Dog
    Front End). Other services can use either ARM or Microsoft Graph. Typically, services that integrate deeply with
    Office 365 use Graph. All others are encouraged to use ARM.

    The Azure portal SDK doesn't require any specific back-end, but does provide extra support for ARM-based resources.
    Please [submit a partner request](http://aka.ms/portalfx/requests) for additional built-in support for standard
    Graph or ARM APIs.

    For Azure Resource Manager (ARM) (Stakeholder: [Ryan Jones](mailto:ibiza-arm@microsoft.com)):
    - [ARM wiki (internal only)](http://sharepoint/sites/AzureUX/Sparta/SpartaWiki/Sparta%20Wiki.aspx)
    - [Onboarding FAQ (intenral only)](http://sharepoint/sites/AzureUX/Sparta/SpartaWiki/Sparta%20Onboarding%20FAQ.aspx)
    - External teams should [email the ARM team](mailto:aux-arm-leads@microsoft.com?subject=[Onboarding%20Request]%20to%20register%20&lt;RP%20Name&gt;)

4. **CSS (Support)** (Stakeholders: [Wes Penner, CEGRM](mailto:ibiza-css@microsoft.com?subject=CSS%20intake%20questions))

    [Start **CSS** onboarding](http://spot/intake) at least 3mos before public preview to ensure your customers can use
    Azure support.

5. **Azure.com** (Stakeholders: [Elena Salaks, Guy Burstein](mailto:ibiza-azure@microsoft.com))

    All new services should be listed in [azure.com](https://azure.microsoft.com). This isn't a requirement for onboarding
    the portal, but service categorization is the same between the azure.com Products menu, portal Services menu, and the
    Azure Marketplace. The long-term goal is for all 3 to be the exact same, where services aren't listed in the portal
    unless they're also on azure.com.

    Plan ahead for all the outbound communication, blogging, and marketing work to publicize your services as it goes out
    to customers, in particular if your release time needs to be aligned with the Azure events and conferences. For preview
    release, this could be an optional requirement, but for GA, your localized azure.com content and service updates plan
    are exit criteria that will require the stakeholders to sign off.

    For more information about azure.com onboarding, see [http://acomdocs.azurewebsites.net](http://acomdocs.azurewebsites.net).

6. **Common Engineering Criteria (CEC)** (Stakeholder: [Duke Kamstra](mailto:ibiza-cec@microsoft.com))

    The Microsoft Common Engineering Criteria (CEC) program was designed to establish a set of engineering requirements
    across all products. Meeting these requirements is critical to the success of Azure. Every extension is required to
    be listed in the [CEC Scorecard](https://azuremetrics.cloudapp.net/scorecards/cec). Onboard your service to the CEC
    Scorecard using the CEC Fundamental Portal (CFP):

   1. Add your service to ServiceTree: https://servicetree.msftcloudes.com
   2. Request your service be "Active"
   3. If not in C+E, go to Dependencies to define a depndency on the CEC Scorecard service (C+E services are automatically added)
   4. Complete metadata in ServiceTree to enable the automation for various KPIs
   5. Complete the requirements for each release stage: https://cecfundamentals

7. **Internationalization** (Stakeholder: [Lynne Dong](mailto:ibiza-interntnl@microsoft.com))

    Nearly 70% of Azure users are from outside of the United States. It’s important to make Azure a globalized product,
    and there are a few requirements under the "Internationalization" criteria you need acour service is required to
    support the same set of languages as the Portal for GA. Learn more about [internationalization requirements](http://aka.ms/azureintlrequirements).

8. **Azure Compliance** (Stakeholders: [Azure Compliance team](azcompl))

    Compliance criteria and practices are defined in [Quality Essentials](https://microsoft.sharepoint.com/teams/QualityEssentials/SitePages/GettingStarted.aspx)
    throughout our development cycle. These ensure services meet the Trusted Cloud commitments outlined in the [Microsoft Azure Trust Center](http://azure.microsoft.com/en-us/support/trust-center/)
    for our customers. There are mandatory procedures as Preview and GA requirement, and to be revisited for every
    release cycle. QE provides the UI access to manage the release policies and procedures for each compliance. The tool
    can be installed from [http://qe](http://qe).

    QE tracks the following:
    - Accessibility
    - Global readiness
    - Global trade compliance
    - License terms
    - Open source software
    - Privacy
    - Security Development Lifecycle (SDL)
    - Software integrity

    Some of the procedures such as Accessibility, GB Certificate, Privacy, and Security are also measured in the
    [CEC Scorecard](http://cecfundamentals/Scorecard/Scorecard) and exit criteria for management review and tracking.
    These requirements apply to both the portal fx and extensions. Since Fx provides the common infrastructure and UI
    controls that govern the data handling and UX, hence some of the compliance work for extensions would be identical
    across in Ibiza, and rationally be mitigated by the Framework. For example, Accessibility support on keyboard
    navigation and screen reader recognition, as well as the regional format and text support to meet globalization
    requirement are implemented at the controls that Framework distributed.  Same for Security threat modeling,
    extension authentication to ARM, postMessage/RPC layer and UserSettings, etc. are handled by Framework. To minimize
    the duplicate efforts on those items Fx provides some level of "blueprint" documentation you can use as a reference
    for compliance procedures. You are still responsible to go through the tools and submit the results for approval
    before shipping your extension. Contact [Amit Modi](mailto:ibiza-onboading-kick@microsoft.com)
    for any questions about Fx coverage.

   | Policy | Fx coverage |
   |--------|-------------|
   | [Accessibility](/portal-sdk/generated/index-portalfx-extension-development.md) | Generic control supports on keyboard, focus handling, touch, screen reader, high contrast, and theming |
   | Global Readiness | Localizability, regional format, text support, China GB standard |
   | Privacy | User settings data handling, encryption, and authentication |
   | SDL | Threat modeling |

9. **Build your portal extension!** (see below)



<a name="onboarding-portal-extension"></a>
## Portal extension

Ready to write your first Azure portal extension? Here are a few resources to get you started:
 
1. **[Download the SDK](http://aka.ms/portalfx/download)**

2. **[Read the docs](http://aka.ms/portalfx/documents)**

   Our doc site provides the technical details while you are building your extension. The
   [Getting Started](/portal-sdk/generated/index-portalfx-extension-development.md#getting-started)
   section will guide you through how it works, build the extension, as well as the debugging tips during your code development.

3. **[View the samples](http://aka.ms/portalfx/samples#blade/SamplesExtension/SDKBlade)**

   The Fx team runs a battery of tests using samples that are available as part of the downloaded SDK as well as available from the DOGFOOD (DF) environment. Browse through the samples to explore live examples of APIs.

4. **<a href="mailto:ibiza-onboading-kickoff?subject=Extension feasibility review">Setup a UX feasibility review</a>**

   Before starting to build your extension, please setup time to review your design and ensure your desired outcome is
   feasible.

5. **Join the right groups**:
   - PMs should join [ibizapartners-pm](http://igroup/join/ibizapartners-pm)
   - Devs should join [ibizapartners-dev](http://igroup/join/ibizapartners-dev)
   - To be notified about upcoming breaking changes, join [ibizabeak](http://igroup/join/ibizabreak)

6. **[Ask questions on //stackoverflow](https://stackoverflow.microsoft.com)**

   Join the community in https://stackoverflow.microsoft.com and let us know if you have any questions. (Don't forget to
   tag questions with "ibiza" or related tag.)

7. **[Side-load your extension for local testing](/portal-sdk/generated/index-portalfx-extension-development.md#debugging-testing-in-production)**

   Side-loading allows you to test and debug your extension locally against any environment. This is the preferred method of testing.

9. **Marketplace integration**

   At a high level, each icon you see in the Azure Portal Marketplace is referred to as a Gallery item. Gallery items
   take the form of a file with the .azpkg extension. You can think of this file as a zip which contains all assets for
   your gallery item: icons, screenshots, descriptions.

   **PROD**: The Marketplace team accepts fully finished .azkpg files from your team and performs upload to Production <a HREF="mailto:1store@microsoft.com?subject=Marketplace Onboarding Request&body=Attach your *.azpkg to this email, fill in the replacements and send.%0A%0AHi 1store, I would like to onboard the attached package to Prod. %0A%0AIn addition to the Marketplace I &lt;do/don't&gt; want to be included in the '+' New flyout experience">Click to request 1store onboarding</a> your gallery package.

   **DOGFOOD**: Use AzureGallery.exe to upload items to DOGFOOD using the following command:

```
AzureGallery.exe upload -p ..\path\to\package.azpkg -h [optional hide key]
```

   In order to use the gallery loader you will need to set some values in the AzureGallery.exe.config file for details see [AzureGallery.exe docs](#gallery-items). For dev/test scenarios see [Test In Prod](#gallery-development)

0. **Register your extension**

   Once your service name is finalized, request to have your extension registered in all environments. Once deployed to
   DOGFOOD (aka DF), contact the Fx team to request that it be enabled (if applicable). Your extension will be enabled
   in production once all exit criteria have been met.

   Extension names must use standard extension name format: `Company_BrandOrSuite_ProductOrComponent` 
   (e.g. `Contoso_Azure_{extension}` or `Microsoft_Azure_{extension}`). Set the extension name in `extension.pdl` as
   follows:

```xml
<Extension Name="Company_BrandOrSuite_ProductOrComponent" Preview="true">
```

   Extension URLs must use a standard CNAME pattern. Create CNAMEs using
   [Microsoft's DNS](http://msinterface/form.aspx?ID=4260) (use any Azure property as the identity).

   | Environment     | URL |
   | --------------- | ----- |
   | **DOGFOOD**     | `df.{extension}.onecloud-ext.azure-test.net` |
   | **PROD**        | `main.{extension}.ext.azure.com` |
   | **BLACKFOREST** | `main.{extension}.ext.microsoftazure.de` |
   | **FAIRFAX**     | `main.{extension}.ext.azure.us` |
   | **MOONCAKE**    | `main.{extension}.ext.azure.cn` |

   Use a wildcard SSL cert for each environment to simplify maintenance (e.g. `*.{extension}.onecloud-ext.azure-test.net`
   or `*.{extension}.ext.azure.com`). If your team is building separate, independent extensions, you can also use
   `{extension}.{team}.ext.azure.com` and create a wildcard SSL cert for `*.{team}.ext.azure.com` to simplify overall
   management. Internal teams can create SSL certs for DF using [http://ssladmin](http://ssladmin). Production certs
   must follow your organizations PROD cert process -- **do not use SSL Admin for production certs**.

   **NOTE** : Registering an extension in Portal requires deployment so it can take almost 10 days. Please plan accordingly.

   [Request to register your extension (internal only)](https://aka.ms/portalfx/newextension) and email the work item id
   to [ibizafxpm](mailto:ibizafxpm@microsoft.com?subject=Register%20extension). You'll automatically be notified when the
   configuration change is pushed to PROD. External teams can
   <a href="mailto:ibizafxpm@microsoft.com?subject=[Onboarding Request] Add &lt;Name&gt; extension to the portal&body=Extension name:  Company_[BrandOrSuite_]ProductOrComponent (e.g. Contoso_SomeSku_SomeProduct or Contoso_SomeProduct)%0A%0AURLs  (must adhere to pattern)%0APROD-- main.&lt;extension&gt;.ext.contoso.com%0A%0AContact info%0ABusiness Contacts:_________%0ADev leads: _________%0APROD on-call email: _________%0A">submit their request via email</a>.

1. **[Exit criteria + quality metrics](#portalfx-onboarding-exitcriteria)**

   Every extension must meet required [exit criteria / quality metrics before it will be enabled.

For any other questions, don’t hesitate to ask us on [https://stackoverflow.microsoft.com](https://stackoverflow.microsoft.com).

 <h1 name="portalfx-onboarding-exitcriteria"></h1>
 ## Exit criteria & quality metrics

In order to meet customer expectations and continue to increase customer satisfaction, the following quality metrics
are tracked for every extension:

1. Performance
2. Reliability
3. Usability
4. Accessibility
6. Feature adoption

<a name="onboarding-portal-extension-performance-stakeholder-sean-watson-mailto-ibiza-perf-microsoft-com"></a>
### Performance (Stakeholder: <a href="mailto:ibiza-perf@microsoft.com">Sean Watson</a>)

**All blades must meet the required blade reveal time of <4 seconds for the 80th percentile** before being enabled in
PROD. Extensions must be enabled in MPAC to start tracking performance. Resource and Create blades are tracked
explicitly. All other blades are rolled up into **Weighted Experience Score (WxP), which must be >80**. WxP
determines the percentage of blade usage that meets the performance bar.

Blade reveal time is the time it takes for all the parts above to fold to call revealContent() (load 1st level data)
or to resolve onInputSet() promises, whichever is earlier.

MPAC and PROD performance is included in weekly status emails and each team is expected to investigate regressions.

See also:
- [Dashboard](http://aka.ms/portalfx/dashboard/extensionperf)
    - [Join auxdatapartners](http://igroup/join/auxdatapartners) for access
- [Checklist](/portal-sdk/generated/index-portalfx-extension-monitor.md#performance-checklist)
- [Portal COP](/portal-sdk/generated/index-portalfx-extension-monitor.md#portalcop)
- [Best pracitces](/portal-sdk/generated/index-portalfx-extension-monitor.md#performance-best-practices)
- [#ibiza-performance on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-performance)
- [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-performance)


<a name="onboarding-portal-extension-reliability-stakeholder-sean-watson-mailto-ibiza-reliability-microsoft-com"></a>
### Reliability (Stakeholder: <a href="mailto:ibiza-reliability@microsoft.com">Sean Watson</a>)

Every extension, blade, and part must meet the **reliability SLA**. Extension, resource blade, and Create blade
reliability metrics must be met before your extension will be enabled in PROD. Extensions must be enabled in MPAC to
start tracking reliability.

MPAC and PROD reliability is included in weekly status emails and each team is expected to investigate regressions.

See also:
- [#ibiza-performance on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-performance)
- [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-performance)


<a name="onboarding-portal-extension-usability-stakeholder-angela-moulden-ibiza-usability-microsoft-com"></a>
### Usability (Stakeholder: <a href="ibiza-usability@microsoft.com">Angela Moulden</a>)

Each service must define the critical, P0 scenarios for their business. These scenarios must be usability tested to
ensure 80% success rates and an experience score of 80 (based on a short survey). Usability must be measured by
testing at least 10 participants.


<a name="onboarding-portal-extension-accessibility-stakeholder-paymon-parsadmehr-ibiza-accessibility-microsoft-com"></a>
### Accessibility (Stakeholder: <a href="ibiza-accessibility@microsoft.com">Paymon Parsadmehr</a>)

Similar to the usability bar, every service must meet the Microsoft standards for accessibility.

- [Accessibility documentation](/portal-sdk/generated/index-portalfx-extension-accessibility.md)
- [#ibiza-accessibility on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-accessibility)
- [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-accessibility)


<a name="onboarding-portal-extension-feature-adoption"></a>
### Feature adoption

All extensions are required to complete the following before being enabled in PROD. None are required to be enabled
in MPAC. Track status on the [feature adoption sign-off dashboard](http://aka.ms/portalfx/dashboard/featureadoption/signoff)
(doesn't include menu blade for services [as opposed to resources], deployment success rates, Create dropdowns/PCv3, or
Browse menu placement).

1. **Menu blade** (aka resource menu; Stakeholders: [Sean Watson, Edison Park](mailto:ibiza-menu-blade@microsoft.com))

    All services must implement the menu blade instead of the Settings pattern. ARM resources should opt in to the
    resource menu for a simpler, streamlined menu.

    Every service must include the following menu items:
    - Resource health -- Check the health of any resource from the resource blade via settings (Stakeholder: Bernardo Alfredo Munoz)
    - Troubleshoot -- Have a [Troubleshoot link](onenote:https://microsoft.sharepoint.com/teams/WAG/EngSys/Supportability/SiteAssets/Supportability%20Notebook/CustomerEnablement.one#Overview&section-id={6468807B-191F-4A37-BB00-C9C0F820459D}&page-id={B7A17DE5-7A04-4193-B1EB-CFD811F233B8}&end) in the resource menu to surface self-help solutions on common issues (Stakeholder: [AzSFAdoption](AzSFAdoption@microsoft.com))
    - Create support request -- Be able to create a support request from the menu (Stakeholder: Ganga Narayanan)

    See also:
    - [#ibiza-blades-parts on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-blades-parts) for menu blade questions
    - [#ibiza-resources on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-resources) for resource menu questions
    - [Ask a menu blade question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-blades-parts)
    - [Ask a resource menu question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-resources)

2. **Create success** (Stakeholder: [Paymon Parsadmehr](mailto:ibiza-create@microsoft.com))

    Every Create blade must meet the create success rate standard. For latest numbers see Power BI. 
    If create workflow success drops 5% over a rolling 24h period with 50+ creates, a sev 2 incident will be filed.
    This covers every error that causes Creates to fail after the user clicks the Create button. Extensions/RPs are responsible for validating all inputs to ensure the user cannot click the create button unless that create will be successful. 
    Services that use template deployment must opt in to RP registration checks, deployment validation, and required permission checks to avoid common errors.

    See also:
    - [#ibiza-create on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-create)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-create)
 
3. **Activity logs** (Stakeholder: [Rajesh Ramabathiran](mailto:ibiza-activity-logs@microsoft.com))

    Activity/event/operation/audit logs must be available from the menu for all services. Subscription-based resources
    (not just tracked resources) get this for free when implementing the resource menu. All other services are
    required to add the equivalent experience for their service.

4. **Create blades** (Stakeholder: [Michael Flanakin, Paymon Parsadmehr](mailto:ibiza-create@microsoft.com))

    All Create blades must be a single blade. Do not use wizards or picker blades. Use form sections and dropdowns.
    Subscription-based resources must use the built-in subscription, resource group, location, and pricing dropdowns;
    especially in Create blades. These each cover common scenarios that will save time and avoid deployment failures.

    See also:
    - [Create documentation](/portal-sdk/generated/index-portalfx-extension-development.md#common-scenarios-building-create-experiences)
    - [#ibiza-create on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-create)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-create)

5. **PCv3** (Stakeholder: [Paymon Parsadmehr](mailto:ibiza-create@microsoft.com))

    Use Parameter Collector v3, especially for Create blades. Do not use v1 or v2 anywhere. The newer version has
    improved APIs, performance, and telemetry.

    See also:
    - [Parameter collection documentation](/portal-sdk/generated/index-portalfx-extension-development.md#introduction-to-parameter-collection)
    - [#ibiza-forms on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-forms)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-forms)
 
6. **Automation options from Create** (Stakeholder: [Paymon Parsadmehr](mailto:ibiza-create@microsoft.com))

    Every service should expose a way to get scripts to automate provisioning. Automation options should include CLI,
    PowerShell, .NET, Java, Node, Python, Ruby, PHP, and REST (in that order). Tracked resources that use the
    built-in template deployment API are opted in by default.

7. **Browse menu placement** (Stakeholder: [Edison Park](mailto:ibiza-browse@microsoft.com))

    All services must be added to a specific category in the Browse/Services menu (under favorites on the left).
    Categorization will be the same as it is for azure.com’s products menu. The Fx team needs to know what asset
    types will be added to ensure your service is placed in the correct categories. (Asset type names are defined in
    extension PDL.)

    See also:
    - [Browse documentation](/portal-sdk/generated/index-portalfx-extension-development.md#common-scenarios-building-browse-experiences)
    - [Asset documentation](/portal-sdk/generated/index-portalfx-extension-development.md#resource-management-assets)
    - [#ibiza-browse on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-browse)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-browse)

The following features are required for all subscription-based resources:

1. **Deployment validation** (Stakeholder: [Paymon Parsadmehr](mailto:ibiza-create@microsoft.com))

    The following validation must be included:
    - Opt in to RP registration checks on the subscription dropdown
    - Specify required permissions on the resource group dropdown
    - Opt in to deployment validation

    See also:
    - [#ibiza-create on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-create)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-create)

2. **Resource move** (Stakeholder: [Edison Park](mailto:ibiza-resourceMove@microsoft.com))

    Being able to move your resource from one subscription or resource group to another.

    See also:
    - [Documentation](#portalfx-resourcemove)
    - [Dashboard](http://aka.ms/portalfx/resourcemove/dashboard)
    - [#ibiza-resources on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-resources)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-resources)

3. **Create from Browse** (Stakeholder: [Edison Park](mailto:ibiza-browse@microsoft.com))

    Have an "Add" command in the Browse blade for that resource.

    See also:
    - [Browse documentation](#portalfx-browse)
    - [Asset documentation](#portalfx-assets)
    - [#ibiza-browse on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-browse)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-browse)

4. **Context menu commands in Browse** (Stakeholder: [Edison Park](mailto:ibiza-browse@microsoft.com))

    Within the Browse blade, your resource specific commands should be available on right-click or when the user
    clicks on the "...".

    Have an "Add" command in the Browse blade for that resource.

    See also:
    - [Browse documentation](#portalfx-browse)
    - [#ibiza-browse on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-browse)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-browse)

5. **Show all resource properties in the Browse column chooser**

    Within the Browse blade, you should have all your resource specific columns available in the column chooser to
    allow users to see data they need.

    See also:
    - [Browse documentation](#portalfx-browse)
    - [#ibiza-browse on StackOverflow](https://stackoverflow.microsoft.com/questions/tagged/ibiza-browse)
    - [Ask a question](https://stackoverflow.microsoft.com/questions/ask?tags=ibiza-browse)

6. **Export template / RP schema**

    ARM RPs must provide a schema for all tracked and nested resource types to ensure they support the export template
    capability. Export template is enabled by default from the resource menu.

    See also:
    - [RP schema documentation](http://aka.ms/rpschema)


