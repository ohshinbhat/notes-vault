Server Components: all next js components are server components (fetch, API, backend)

Client Components: - Components in the Client Component module graph are primarily rendered on the client, but with Next.js, they can also be pre-rendered on the server and hydrated on the client.  `use Client` can sit between server and client component (hooks, onClicks, state)