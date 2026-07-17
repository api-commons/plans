# API Plans

An API Plan is a machine-readable description of the access tiers available for an API—defining what an API consumer has access to, the rate limits and metrics that constrain that access, and what the resources will cost. Plans turn the pricing and packaging of an API into structured, interoperable data instead of prose buried on a pricing page, giving producers a consistent way to describe their offers and giving consumers (and tooling) a reliable way to compare, understand, and integrate against them. Monetization and access are core parts of API operations, and plans are the building block for describing them.

## API Commons

API Plans are an [API Commons](http://apicommons.org) building block—an open, machine-readable schema for describing API access tiers, pricing, and rate limiting, made interoperable as part of the API contract so it can be discovered, referenced, and reused across the APIs.json ecosystem and surfaced through [apis.io](https://apis.io).

## What's in this repo

- [plans-json-schema.yml](plans-json-schema.yml) — The JSON Schema that defines a set of plans.
- [plans-example-1.yml](plans-example-1.yml) — A worked example defining access tiers for the APIs.io API.
- [claude-openai-gemini-plans.yaml](claude-openai-gemini-plans.yaml) — A real-world example capturing the consumer plans for Claude, OpenAI, and Gemini.
- [claude-openai-gemini-pricing.yaml](claude-openai-gemini-pricing.yaml) — A real-world example capturing the API (token) pricing for Claude, OpenAI, and Gemini.

## The Schema

The [plans-json-schema.yml](plans-json-schema.yml) defines a plans document as an array of plan objects, each with:

- **id** — The unique identifier for an API plan.
- **name** — The title or name defining the API plan.
- **description** — A more detailed description of what an API plan is.
- **entries** — An array of the metered entries in the plan, each with a `label`, `description`, `metric`, `limit`, `timeFrame`, `geo`, `unit`, and `price`.
- **elements** — An array of the features (each with a `name`) included in the plan tier.

## Example

The [plans-example-1.yml](plans-example-1.yml) file defines access tiers for the APIs.io API:

```yaml
- id: starter
  name: Starter
  description: The default API access plan, where every new account begins...
  entries:
    - label: API calls
      description: to the search API
      metric: calls
      limit: 25
      timeFrame: day
      geo: US
      unit: 1
      price: "Free"
  elements:
    - name: Free
    - name: Self Service Support
    - name: Easiest to Start
    - name: No commitment
```

The [claude-openai-gemini-plans.yaml](claude-openai-gemini-plans.yaml) and [claude-openai-gemini-pricing.yaml](claude-openai-gemini-pricing.yaml) files apply the same modeling approach to real AI providers, capturing both their consumer subscription plans and their usage-based API token pricing.

## How It Fits

Plans are one of a growing set of API Commons building blocks that describe the business and technical realities of API operations in a machine-readable way. They cross-link with the [change log](https://github.com/api-commons/change-log), [road map](https://github.com/api-commons/road-map), [teams](https://github.com/api-commons/teams), [use cases](https://github.com/api-commons/use-cases), [guidance](https://github.com/api-commons/guidance), [policies](https://github.com/api-commons/policies), and other building blocks—each a small, reusable schema that can stand alone or be composed together within an APIs.json index.

## Support

This schema is managed using the issues on this GitHub repository. It is in an early stage of development and moving regularly as it is applied to profiling existing APIs and describing new ones. If there is a feature you'd like to see, or you have questions, please submit an issue or email kin@apievangelist.com.

## Part of API Commons

A machine-readable building block from **[API Commons](https://apicommons.org)** — open specifications and schemas for the APIs you produce and consume. See all building blocks and tools at **[apicommons.org](https://apicommons.org)** and the tools at **[apicommons.org/tools](https://apicommons.org/tools/)**.

**Related building blocks**
- [tiers](https://github.com/api-commons/tiers) — the access/service tiers available for an API
- [rate-limits](https://github.com/api-commons/rate-limits) — the rate limits that constrain API access
- [use-cases](https://github.com/api-commons/use-cases) — how an API is actually put to work, tied to its operations
- [road-map](https://github.com/api-commons/road-map) — publish an API's roadmap in a machine-readable way
- [change-log](https://github.com/api-commons/change-log) — publish an API's changelog in a machine-readable way
