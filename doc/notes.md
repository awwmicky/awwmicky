# Notes

- use element tags for markdown
- what is StyleLint? https://stylelint.io/

## web security
- rate limit endpoint
  - client > limiter > server
- upload limits
  - excess file/message size
- user input data
  - worst case scenario, test case
  - expect: data type \ content \ signiture
  - avoid sequel injection \ always sanetize
- sql/nosql injection
  - don't let user access/execute things directly
  - specify logic code, then test w/ database
- security by obscurity
  - expose what can be exploited
  - no need for it to be handled in production/client
  - disable SQL errors
- dumb services
  - have a logic layer for services
  - easy does not mean secure
  - it should not be exposed in public
  - learn to open & close

## project idea
- npm package (library)
  - TypeScript \ Jasmine
  - GitHub Action (CI/CD)
  - package version/release/zip
- custom API
  - security \ Swagger \ rate-limit
- unit test
  - Jest \ Jasmine \ Cypress
  - React \ Node
- Search App
  - React \ TypeScript \ GraphQL
- Control/Endpoint
  - Deno.js \ Nest.js \ Fastify.js
- Blog App
  - JAM Stack \ SEO \ Next.js
- pre-loader
  - css skeleton \ lazy load
- animation 
  - three.js \ GSAP.js \ Framer Motion

## Performance Cost
- render cycle \ bottleneck
- load time \ scalability \ optimization
- portability \ maintainability \ workflow experience