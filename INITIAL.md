## FEATURE:
All-in-One ERP System for Company Operations

This ERP is designed as a modular, cloud-first platform that unifies all critical company processes in one environment. Unlike older, overly complex ERPs, this system focuses on simplicity, automation, and adaptability. Each module can stand alone or integrate seamlessly with others, so the company can start small and grow the system as needs expand.

Key pillars of the ERP:
- **Integration-first**: Works natively with e-commerce, banking, POS, and external APIs.
- **Automation-heavy**: Reduces manual data entry with AI-assisted workflows.
- **User-focused design**: Minimal, mobile-ready, bilingual (Thai/English), and role-based dashboards for clarity.
- **Scalable**: From small business to enterprise without system migration.

### Goal
Build a modular ERP system tailored to our company's needs, covering Finance, Inventory, HR, and Sales.  
The system should be **scalable**, **modular**, and **easy to extend**.

### Core Modules

#### 1. Finance Module
- Track income, expenses, profit/loss with automated categorization
- Generate invoices & payment records with Thai tax compliance
- Automated monthly/annual reports (P&L, Balance Sheet, Cash Flow)
- Multi-currency support (THB primary, USD/EUR secondary)
- Bank reconciliation automation via API connections

#### 2. Inventory Module  
- Stock tracking with minimum level alerts and auto-reorder suggestions
- Real-time updates from sales and purchases across all channels
- Barcode/QR integration for quick scanning and mobile inventory management
- Batch/lot tracking for expirable products
- Multi-location warehouse support

#### 3. HR Module
- Employee onboarding with digital document management
- Attendance tracking (clock-in/out, GPS verification for remote work)
- Leave management with approval workflows
- Payroll integration with Finance module (Thai labor law compliance)
- Performance review cycles and goal tracking

#### 4. Sales Module
- Customer CRM with contact history, preferences, and communication logs
- Quote-to-cash workflow (quotes → orders → invoices → payments → delivery)
- Sales performance dashboards with forecasting
- Customer portal for order status and history
- Integration with existing e-commerce platforms

### Technical Architecture Requirements
- **Frontend**: Progressive Web App (PWA) with offline capabilities
- **Backend**: Microservices architecture for true modularity
- **Database**: PostgreSQL with proper indexing for multi-tenant architecture
- **Authentication**: Role-based access control (RBAC) with SSO support
- **APIs**: RESTful APIs with comprehensive documentation and rate limiting
- **Deployment**: Docker containers with Kubernetes orchestration

### Constraints
- Should be modular (each part can work independently but integrates smoothly)
- Web-based first (desktop + mobile responsive with PWA capabilities)
- Scalable database design supporting multi-tenancy
- Integration-ready (APIs for third-party tools like accounting software, e-commerce platforms)
- Low barrier for non-technical staff to use (intuitive UI/UX)
- Must handle Thai language properly (UTF-8, Thai date formats, address formats)
- Comply with Thai business regulations and tax requirements

### Success Criteria
- Internal team can manage daily operations without manual spreadsheets
- Real-time dashboards provide actionable business insights
- Reduces repetitive admin tasks by at least 40%
- System can onboard new users with less than 2 hours of training
- 99.9% uptime with sub-2-second page load times
- Successfully handles 10x current transaction volume without performance degradation

## DOCUMENTATION:

### Technical References
- **Thai Tax & Compliance**: 
  - Thai Revenue Department API documentation for e-filing
  - Thai Labor Protection Act requirements for HR compliance
- **Integration APIs**:
  - Shopify/WooCommerce APIs for e-commerce integration
  - Thai banking APIs (SCB Easy, Kbank, BBL) for payment reconciliation
  - Line Notify API for real-time alerts to mobile devices
- **UI/UX Standards**:
  - Thai Government Digital Service Standards
  - Web Content Accessibility Guidelines (WCAG) 2.1
- **Database Design**:
  - Multi-tenant SaaS database patterns
  - PostgreSQL performance optimization guides
- **Security Standards**:
  - OWASP Web Application Security Testing Guide
  - Thai Personal Data Protection Act (PDPA) compliance requirements

### Business Process References
- Current company workflows and approval processes
- Existing data formats and export requirements
- Integration points with current tools (accounting software, CRM, etc.)
- User personas and role definitions for each department

## OTHER CONSIDERATIONS:

### AI Coding Assistant Common Pitfalls to Avoid:

1. **Database Design Issues**:
   - Don't create overly normalized databases that hurt performance
   - Ensure proper indexing from the start, not as an afterthought
   - Design for data archiving and purging from day one
   - Include soft deletes and audit trails for all critical entities

2. **Thai-Specific Requirements Often Missed**:
   - Thai address format validation (district/amphoe/province hierarchy)
   - Thai ID number validation algorithms
   - Buddhist calendar support alongside Gregorian
   - Proper Thai text sorting and search capabilities
   - Thai number formatting (comma separators, currency display)

3. **Real-World Business Logic Complexities**:
   - Partial payments and payment terms handling
   - Complex discount structures and promotional pricing
   - Inventory reservations and allocation logic
   - Multi-step approval workflows with delegation
   - Timezone handling for multi-location operations

4. **Security & Compliance Oversights**:
   - Don't implement basic auth - use proper OAuth2/JWT
   - Encrypt sensitive data at rest and in transit
   - Implement proper audit logging for financial transactions
   - Rate limiting and DDoS protection for APIs
   - GDPR-style data deletion capabilities for PDPA compliance

5. **Performance & Scalability Issues**:
   - Implement pagination for all list views from the start
   - Use database connection pooling and query optimization
   - Plan for horizontal scaling with stateless services
   - Implement proper caching strategies (Redis/Memcached)
   - Background job processing for heavy operations

6. **Integration Gotchas**:
   - Always implement retry logic with exponential backoff for external APIs
   - Handle API rate limits gracefully with queuing
   - Design for eventual consistency in distributed operations
   - Implement proper error handling and user feedback for failed integrations
   - Create comprehensive logging for troubleshooting integration issues

7. **User Experience Considerations**:
   - Implement optimistic UI updates with rollback capability
   - Provide clear loading states and progress indicators
   - Design mobile-first responsive layouts, not desktop-down
   - Include keyboard shortcuts for power users
   - Implement proper error messages in both Thai and English

### Development Approach:
- Start with Finance module as it has the most critical business impact
- Build comprehensive API documentation from day one
- Implement automated testing for all business logic
- Create development, staging, and production environments
- Use feature flags for gradual rollout of new functionality
