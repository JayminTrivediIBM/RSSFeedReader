# Tasks: MVP RSS Reader

**Input**: Design documents from `/specs/001-mvp-rss-reader/`

**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2)
- Include exact file paths in descriptions

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Establish the web application structure and local development baseline.

- [ ] T001 Create backend and frontend project structure aligned with the implementation plan
- [ ] T002 Configure backend API and frontend UI startup settings for local development
- [ ] T003 [P] Verify routing and startup configuration so the app can be launched locally

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Create the shared infrastructure required before user story work can begin.

- [ ] T004 Create a shared subscription model in backend/src/models/Subscription.cs
- [ ] T005 Implement an in-memory subscription service in backend/src/services/SubscriptionService.cs
- [ ] T006 Implement API endpoints for listing and adding subscriptions in backend/src/api/SubscriptionsController.cs
- [ ] T007 Add configuration and CORS setup so the frontend can call the backend locally
- [ ] T008 Create a frontend service for calling the subscriptions API in frontend/src/services/SubscriptionApiService.cs

**Checkpoint**: Foundation ready - user story implementation can now begin.

---

## Phase 3: User Story 1 - Add a feed subscription (Priority: P1) 🎯 MVP

**Goal**: Allow a user to add a feed URL and see it appear in the subscription list.

**Independent Test**: A user can open the app, enter a feed URL, submit it, and see the new subscription displayed immediately.

### Implementation for User Story 1

- [ ] T009 [P] [US1] Create the subscriptions UI page in frontend/src/pages/Subscriptions.razor
- [ ] T010 [P] [US1] Add the input form and submit handling for adding subscriptions in frontend/src/pages/Subscriptions.razor
- [ ] T011 [US1] Connect the UI to the backend API to add a subscription in frontend/src/services/SubscriptionApiService.cs
- [ ] T012 [US1] Display the updated subscription list after a successful add in frontend/src/pages/Subscriptions.razor
- [ ] T013 [US1] Handle empty submissions and duplicate subscriptions in backend/src/services/SubscriptionService.cs
- [ ] T014 [US1] Return appropriate API responses for success and validation errors in backend/src/api/SubscriptionsController.cs

**Checkpoint**: User Story 1 should be fully functional and independently testable.

---

## Phase 4: User Story 2 - Review the current subscription list (Priority: P2)

**Goal**: Show the user the current list of subscriptions and present a clear empty state.

**Independent Test**: A user can open the app and see either an empty state or the current list of subscriptions.

### Implementation for User Story 2

- [ ] T015 [P] [US2] Add an empty-state message for the subscriptions UI in frontend/src/pages/Subscriptions.razor
- [ ] T016 [US2] Load and display the current subscription list from the backend in frontend/src/pages/Subscriptions.razor
- [ ] T017 [US2] Ensure the UI refreshes the list after page load and after add operations in frontend/src/pages/Subscriptions.razor
- [ ] T018 [US2] Return the current subscription collection from the backend in backend/src/api/SubscriptionsController.cs

**Checkpoint**: User Stories 1 and 2 should both work independently.

---

## Phase 5: Polish & Cross-Cutting Concerns

**Purpose**: Finish the MVP experience and verify the flow end to end.

- [ ] T019 [P] Review the UI copy and empty-state messaging in frontend/src/pages/Subscriptions.razor
- [ ] T020 Run the backend and frontend locally and verify the add/list flow from the quickstart
- [ ] T021 Update documentation or notes if any configuration or startup details change
