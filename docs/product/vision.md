# GENNAKER
## Product Vision

**Document status:** Draft 0.2  
**Project:** GENNAKER  
**Document type:** Product definition

---

## 1. Vision

GENNAKER is a multi-user, multi-portfolio investment management platform built around a reliable accounting foundation and an extensible, API-first architecture.

Its purpose is to provide a structured environment in which investment portfolios can be created, managed, observed, and eventually compared. It will give users the ability to explore different investment approaches, evaluate their outcomes, and understand the relationship between decisions and performance.

The platform will be designed from the outset to support both human interaction and independent software clients. A documented REST API will serve as the primary interface to the system, allowing its capabilities to be accessed through the web application, command-line tools, and, eventually, automated agents.

GENNAKER will prioritize correctness, transparency, adaptability, and disciplined engineering over the accumulation of features.

The initial product will operate entirely in a virtual investment environment. It will not execute real trades or provide investment advice.

## 2. The Opportunity

Investment experimentation involves more than selecting assets and observing whether their prices rise or fall.

Meaningful evaluation requires a reliable record of transactions, an accurate representation of portfolio holdings and cash balances, current and historical market information, and the ability to calculate outcomes consistently.

It also requires the ability to explore different approaches independently. Investment methodologies should not be inseparably tied to a single portfolio or set of assumptions.

GENNAKER addresses this by providing a common platform for portfolio accounting, market data management, and future strategy evaluation.

Rather than building a collection of disconnected tools, the project will establish a coherent system in which each capability is exposed through a consistent interface and supported by a well-defined underlying model.

## 3. Product Concept

GENNAKER will provide a centralized system of record for virtual investment portfolios belonging to multiple independent users.

Each user will be able to maintain multiple portfolios, each with its own transactions, cash balance, holdings, and investment history.

The platform will distinguish between three fundamental areas of responsibility:

**Portfolio Accounting**

The authoritative record of investment activity. Transactions establish the financial history of a portfolio, from which holdings and cash balances are derived.

**Market Data**

An external source of asset prices and related observations used to value portfolio holdings. Market observations will be recorded independently of portfolio accounting and associated with their source and time of observation.

**Investment Strategies**

A potential future capability for defining, exploring, and evaluating investment approaches. Strategies are intentionally left undefined at this stage. Their nature, representation, and relationship to portfolios will be determined through subsequent exploration.

The initial release will establish the portfolio accounting and market-data foundations, along with the interfaces necessary to build upon them.

## 4. Product Principles

### 4.1 Correctness Before Convenience

Financial records and calculations must be accurate, deterministic, and auditable.

Monetary values will use appropriate decimal arithmetic. Portfolio balances and holdings will be derived from authoritative transaction records rather than maintained as loosely synchronized values.

Corrections to historical activity must preserve an understandable record of what occurred.

### 4.2 API-First Architecture

The REST API is the primary interface to GENNAKER.

The web application, command-line client, and future automated systems will consume the same application interface. No client will bypass the API to interact directly with the database.

The API will be documented, consistent, and designed for independent integration.

### 4.3 Separation of Responsibilities

Portfolio accounting, market data, investment strategies, and user interaction are distinct responsibilities.

The accounting system must remain reliable regardless of how investment decisions are generated.

Future analytical or AI-driven components must not be able to compromise the integrity of the underlying accounting records.

### 4.4 Transparency and Auditability

The platform should make it possible to understand how a portfolio arrived at its current state.

Transactions, price observations, and valuations should have clear provenance. Calculations should be reproducible from recorded inputs and defined calculation rules.

### 4.5 Derived Information Should Remain Derived

The underlying records of investment activity and market observations are authoritative.

Performance measurements, rankings, comparisons, and other analytical results should generally be calculated from those records when requested, rather than maintained as potentially stale portfolio properties.

Caching derived results may be introduced where justified by performance or usability requirements.

### 4.6 Security and Data Isolation

GENNAKER will support multiple independent users from its initial release.

User data must be appropriately protected, and access to portfolios and associated records must be authorized on every relevant operation.

Security will rely on established authentication, authorization, credential-management, and data-protection practices rather than custom security mechanisms.

### 4.7 Extensibility Without Premature Complexity

The initial architecture should accommodate future capabilities without requiring them to be implemented prematurely.

The system should be modular and well-defined, but not burdened by speculative abstractions or infrastructure that does not serve an established requirement.

### 4.8 Professional Engineering Practice

Requirements, architectural decisions, testing, documentation, deployment, and release management will be treated as integral parts of the product rather than activities performed after implementation.

## 5. Intended Users

GENNAKER is intended for individuals who want to create, manage, and evaluate virtual investment portfolios.

The architecture will also accommodate future use by:

- Developers building independent applications against the GENNAKER API.
- Researchers or enthusiasts comparing investment approaches.
- Users interested in evaluating investment methodologies under different assumptions and conditions.
- Automated systems and agents interacting with portfolios programmatically.

The initial product will support multiple independent user accounts, each with appropriately isolated data.

Organizational accounts, collaborative portfolios, subscription management, and enterprise permissions are not initial requirements.

## 6. Initial Release: GENNAKER 1.0

The first release will establish a complete, usable, multi-user portfolio management platform.

It will provide the ability to:

1. Register and authenticate independent users.
2. Create and maintain multiple portfolios per user.
3. Register and manage investable assets.
4. Record purchases, sales, and associated transaction details.
5. Maintain accurate cash balances and asset positions.
6. Retrieve current market prices from an external data provider.
7. Record and retain historical market-price observations, subject to applicable data licensing.
8. Calculate portfolio valuations using available market data.
9. Review transaction histories and portfolio composition.
10. Access portfolio functionality through a documented REST API.

The platform will capture the underlying financial records required to calculate performance metrics in future releases. Comprehensive performance analytics, rankings, and strategy evaluation are not requirements for the initial release.

The release will include:

- A web-based user interface.
- A Node.js and TypeScript API service.
- A PostgreSQL database.
- An independent C# command-line client consuming the REST API.
- An external market-data integration.
- Automated testing and API documentation.
- Containerized development and deployment environments.
- A continuous integration and deployment pipeline.
- An initial cloud deployment using AWS.

## 7. Future Direction

GENNAKER's longer-term potential extends beyond portfolio bookkeeping.

The platform is intended to become an environment for evaluating investment approaches and, eventually, integrating autonomous or semi-autonomous decision-making systems.

Potential future capabilities include:

- Independently defined investment strategies.
- Strategy-to-portfolio associations.
- Historical performance analysis and comparative evaluation.
- Portfolio rankings and strategy comparisons.
- Automated portfolio management.
- Integration with locally hosted language models.
- Fine-tuned models operating within explicitly defined constraints.
- Autonomous agents interacting with portfolios through the API.
- Multiple strategies or agents operating against separate portfolios for comparative evaluation.

The nature of an investment strategy remains deliberately open. It may eventually represent a methodology, a parameterized ruleset, an executable algorithm, a trained model, an autonomous agent, or some combination of these.

A future integration with locally hosted models, including Ollama-based infrastructure, is a particularly interesting direction.

However, these capabilities are not prerequisites for the initial release.

The distinction between an accounting engine and a decision-making engine is fundamental: GENNAKER must be able to record and explain what happened independently of any system proposing what should happen next.

## 8. Explicit Non-Goals

The initial release will not attempt to:

- Execute real-world financial transactions.
- Connect to brokerage accounts.
- Provide financial advice or investment recommendations.
- Predict market movements.
- Implement autonomous investment agents.
- Integrate language models or fine-tuned AI models.
- Implement investment strategy optimization or automated backtesting.
- Provide comprehensive portfolio performance analytics.
- Support complex financial instruments or derivatives.
- Provide organizational accounts or collaborative portfolio management.
- Provide enterprise subscription or billing functionality.

These exclusions are deliberate scope boundaries, not necessarily permanent product limitations.

## 9. Measures of Success

GENNAKER 1.0 will be considered successful when it demonstrates the following:

**Functional completeness**

Multiple users can independently create and manage portfolios, record investment activity, maintain asset positions, and view portfolio valuations.

**Accounting integrity**

Portfolio balances, holdings, and valuations are calculated consistently from recorded transactions and market observations.

**Market-data integration**

The application retrieves current market prices from an external provider, records observations with appropriate provenance, and communicates data freshness to users.

**Data isolation and security**

Users can access their own portfolios and associated records, but cannot access another user's information without explicit authorization.

**API completeness**

Core functionality is accessible through a documented REST API, independently of the web application.

**Client independence**

The C# command-line application can perform meaningful portfolio operations using only the published API.

**Engineering quality**

The system has automated tests, documented architecture, repeatable development environments, and a functioning CI/CD pipeline.

**Operational readiness**

The application can be deployed to AWS and operated as a coherent service.

**Extensibility**

The architecture provides a clear path toward introducing independently defined investment strategies and programmatic decision-making systems without compromising the accounting foundation.

## 10. Product Identity

The name GENNAKER draws on the asymmetric sailing sail used to capture available wind and convert it into forward motion.

The name is intended to evoke the qualities of good seamanship: discipline, coordination, precision, adaptability, and measured performance.

These qualities also inform the product's philosophy.

GENNAKER is not intended to be a system that simply chases market movements. It is an instrument for organizing information, evaluating decisions, and understanding outcomes.

The product should communicate technical competence and quiet confidence. Its visual identity should be distinctive and considered, avoiding both generic financial-software conventions and overly literal nautical imagery.

---

**End of document**