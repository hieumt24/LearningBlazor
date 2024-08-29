# Introduction to Blazor

## Overview
Blazor is a framework for building interactive client-side web UIs with .NET. Developed and supported by Microsoft as part of the .NET ecosystem, Blazor was first released in 2018 with .NET 3.0. The framework enables developers to:
- Create rich interactive UIs using C# instead of JavaScript.
- Share server-side and client-side application logic written in .NET.
- Render the UI as HTML and CSS, ensuring wide browser support, including mobile browsers.

### Blazor Server
- **Thin client**: Minimal client-side logic, reducing the client-side footprint.
- **Full runtime**: Provides a full .NET runtime on the server.
- **More secure**: Server-side logic is more secure as it is not exposed to the client.
- **UI latency on bad network**: Higher latency can occur if the network is slow or unstable.
- **Harder to scale**: Uses SignalR, which can make it harder to scale under heavy load.

### Blazor WebAssembly
- **Static file hosting**: Blazor WebAssembly apps can be hosted on any web server.
- **Offline support/PWA**: Supports Progressive Web Apps (PWA) and can work offline.
- **Zero latency UI**: UI updates are immediate, as all logic runs on the client.
- **Big download size**: Initial download size can be large, impacting load times.

## Why Blazor?
- **Based on .NET and C#**: .NET developers do not need to learn new frameworks like Vue, Angular, or React.
- **Leverages the .NET ecosystem**: Utilizes existing .NET libraries and tools.
- **Enables code sharing**: Allows sharing code between the frontend and backend.
- **Mature and supported by Microsoft**: Backed by Microsoft with continuous improvements and support.
- **Benefits from .NET performance, reliability, and security**.
- **Rich ecosystem of components**:
  - Paid components: Syncfusion, Infragistics, Progress Telerik, DevExpress, etc.
  - Free components: Radzen, MudBlazor, Blazorstrap, Ant Design Blazor, etc.
- Suitable for applications where user base is not massive, or initial load time is not critical.

## Blazor Components
Blazor applications are based on components, which are the building blocks of the UI. A component in Blazor represents a part of the UI, such as a page, dialog, or data entry form.

- **Components**: .NET C# classes built into .NET assemblies that:
  - Define flexible UI rendering logic.
  - Handle user events.
  - Can be nested and reused.
  - Can be shared and distributed as Razor class libraries or NuGet packages.
- **Razor components**: Inherit from the `ComponentBase` base class.
- **Partial class support**:
  - A single file can contain C# code defined in one or more `@code` blocks, HTML markup, and Razor markup.
  - HTML and Razor markup are placed in a `.razor` file, while C# code is placed in a code-behind file defined as a partial class (`.cs`).
- **Required parameters**: Parameters can be passed to components to manage data and state.

## Rendering in Blazor
Blazor uses a concept called the **RenderTree**, which is a DOM abstraction similar to the Virtual DOM. 

- The RenderTree can be updated more efficiently than the traditional DOM, as it reconciles multiple changes into a single update.
- When a component's state changes, a new copy of the RenderTree is created from the changes, either through code or data binding.
- Before the component re-renders, the current state is compared with the new state, and a diff is produced.
- Only the differences are applied to the DOM during the update, optimizing performance.

## Lifecycle 
- public override async Task SetParametersAsync(ParameterView parameters)
- protected override void OnInitialized()
- protected override async Task OnInitializedAsync()
- protected override void OnParametersSetAsync()
- protected override async Task OnParametesSetAsync()
- protected override bool ShouldRender()
- protected override void OnAfterRender(bool firstRender)
- protected override async Task OnAfterRenderAsync(bool firstRender)
---


