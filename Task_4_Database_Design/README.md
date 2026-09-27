
# Task 4: Designing a Database

## Overview

The fourth task focused on designing a structured database for storing Commonwealth Bank social media data.

The previous task involved analysing unstructured social media information. This task focused on determining how the information could be organised into related tables so that it could be stored, managed, queried, and analysed efficiently.

The database design separates different types of information into subject-based tables and uses primary and foreign keys to establish relationships between them.

## Objectives

The main objectives of the task were to:

- Identify the information that needs to be stored.
- Divide the information into logical tables.
- Define the fields required in each table.
- Identify primary keys.
- Identify foreign keys.
- Define relationships between tables.
- Reduce unnecessary duplication.
- Support data accuracy and integrity.
- Create a structure suitable for reporting and analysis.

## Database Tables

The proposed database contains the following tables:

1. Users
2. Posts
3. Replies
4. Quote_Retweets
5. Mentions
6. Engagement
7. Sentiment
8. Topics
9. Post_Topics

---

## 1. Users

The `Users` table stores information about social media users.

| Field | Description | Key |
|---|---|---|
| `user_id` | Unique identifier for the user | Primary Key |
| `username` | User's social media username | |
| `display_name` | User's displayed name | |
| `account_created_at` | Date the account was created | |
| `verified` | Indicates whether the account is verified | |

### Primary Key

`user_id`

---

## 2. Posts

The `Posts` table stores posts published by Commonwealth Bank or other relevant accounts.

| Field | Description | Key |
|---|---|---|
| `post_id` | Unique identifier for the post | Primary Key |
| `user_id` | User who created the post | Foreign Key |
| `post_text` | Text content of the post | |
| `created_at` | Date and time the post was created | |
| `language` | Language of the post | |
| `post_url` | URL of the original post | |

### Primary Key

`post_id`

### Foreign Key

`user_id` references `Users.user_id`.

---

## 3. Replies

The `Replies` table stores replies made by users to social media posts.

| Field | Description | Key |
|---|---|---|
| `reply_id` | Unique identifier for the reply | Primary Key |
| `post_id` | Post being replied to | Foreign Key |
| `user_id` | User who created the reply | Foreign Key |
| `reply_text` | Text content of the reply | |
| `created_at` | Date and time the reply was created | |
| `language` | Language of the reply | |

### Primary Key

`reply_id`

### Foreign Keys

- `post_id` references `Posts.post_id`
- `user_id` references `Users.user_id`

---

## 4. Quote_Retweets

The `Quote_Retweets` table stores posts where users repost an original post while adding their own comment.

| Field | Description | Key |
|---|---|---|
| `quote_id` | Unique identifier for the quote repost | Primary Key |
| `original_post_id` | Original post being quoted | Foreign Key |
| `user_id` | User who created the quote repost | Foreign Key |
| `quote_text` | Text added by the user | |
| `created_at` | Date and time the quote repost was created | |

### Primary Key

`quote_id`

### Foreign Keys

- `original_post_id` references `Posts.post_id`
- `user_id` references `Users.user_id`

---

## 5. Mentions

The `Mentions` table stores information about users mentioned in posts.

| Field | Description | Key |
|---|---|---|
| `mention_id` | Unique identifier for the mention | Primary Key |
| `post_id` | Post containing the mention | Foreign Key |
| `mentioned_user_id` | User who was mentioned | Foreign Key |
| `mention_position` | Position of the mention within the post | |

### Primary Key

`mention_id`

### Foreign Keys

- `post_id` references `Posts.post_id`
- `mentioned_user_id` references `Users.user_id`

---

## 6. Engagement

The `Engagement` table stores engagement measurements associated with posts.

| Field | Description | Key |
|---|---|---|
| `engagement_id` | Unique identifier for the engagement record | Primary Key |
| `post_id` | Post associated with the engagement | Foreign Key |
| `likes` | Number of likes | |
| `replies` | Number of replies | |
| `reposts` | Number of reposts | |
| `quote_reposts` | Number of quote reposts | |
| `views` | Number of post views | |
| `link_clicks` | Number of link clicks | |
| `measured_at` | Date and time the engagement was measured | |

### Primary Key

`engagement_id`

### Foreign Key

`post_id` references `Posts.post_id`.

---

## 7. Sentiment

The `Sentiment` table stores sentiment analysis results for posts.

| Field | Description | Key |
|---|---|---|
| `sentiment_id` | Unique identifier for the sentiment record | Primary Key |
| `post_id` | Post that was analysed | Foreign Key |
| `sentiment` | Sentiment category such as positive, neutral, negative, or mixed | |
| `sentiment_score` | Numerical sentiment score | |
| `analysis_date` | Date the sentiment analysis was performed | |

### Primary Key

`sentiment_id`

### Foreign Key

`post_id` references `Posts.post_id`.

---

## 8. Topics

The `Topics` table stores the different subjects or themes identified in social media content.

| Field | Description | Key |
|---|---|---|
| `topic_id` | Unique identifier for the topic | Primary Key |
| `topic_name` | Name of the topic | |
| `topic_description` | Description of the topic | |

### Primary Key

`topic_id`

---

## 9. Post_Topics

The `Post_Topics` table connects posts to topics.

A post can belong to multiple topics, and a topic can be associated with multiple posts. This creates a many-to-many relationship between `Posts` and `Topics`.

| Field | Description | Key |
|---|---|---|
| `post_id` | Post associated with the topic | Primary Key / Foreign Key |
| `topic_id` | Topic associated with the post | Primary Key / Foreign Key |

### Primary Key

The combination of:

`post_id + topic_id`

forms a composite primary key.

### Foreign Keys

- `post_id` references `Posts.post_id`
- `topic_id` references `Topics.topic_id`

---

# Relationships

The proposed database contains the following relationships.

### Users and Posts

One user can create many posts.

**Relationship:**

`Users 1 → Many Posts`

---

### Users and Replies

One user can create many replies.

**Relationship:**

`Users 1 → Many Replies`

---

### Posts and Replies

One post can receive many replies.

**Relationship:**

`Posts 1 → Many Replies`

---

### Users and Quote_Retweets

One user can create many quote reposts.

**Relationship:**

`Users 1 → Many Quote_Retweets`

---

### Posts and Quote_Retweets

One original post can be quoted by many users.

**Relationship:**

`Posts 1 → Many Quote_Retweets`

---

### Posts and Mentions

One post can contain multiple mentions.

**Relationship:**

`Posts 1 → Many Mentions`

---

### Users and Mentions

One user can be mentioned in many posts.

**Relationship:**

`Users 1 → Many Mentions`

---

### Posts and Engagement

A post can have one or more engagement records, allowing engagement to be tracked over time.

**Relationship:**

`Posts 1 → Many Engagement`

---

### Posts and Sentiment

A post can have one or more sentiment analysis records, allowing sentiment analysis to be updated or tracked over time.

**Relationship:**

`Posts 1 → Many Sentiment`

---

### Posts and Topics

A post can be associated with multiple topics.

**Relationship:**

`Posts 1 → Many Post_Topics`

---

### Topics and Post_Topics

A topic can be associated with multiple posts.

**Relationship:**

`Topics 1 → Many Post_Topics`

---

### Posts and Topics

Because a post can have multiple topics and a topic can belong to multiple posts, `Posts` and `Topics` have a many-to-many relationship.

This relationship is handled through the `Post_Topics` junction table.

**Relationship:**

`Posts Many ↔ Many Topics`

through:

`Post_Topics`

---

# Database Structure Summary

| Table | Primary Key | Main Purpose |
|---|---|---|
| `Users` | `user_id` | Stores user information |
| `Posts` | `post_id` | Stores social media posts |
| `Replies` | `reply_id` | Stores replies to posts |
| `Quote_Retweets` | `quote_id` | Stores quote reposts |
| `Mentions` | `mention_id` | Stores user mentions |
| `Engagement` | `engagement_id` | Stores post engagement metrics |
| `Sentiment` | `sentiment_id` | Stores sentiment analysis |
| `Topics` | `topic_id` | Stores topic information |
| `Post_Topics` | `post_id + topic_id` | Connects posts and topics |

# Benefits of the Proposed Design

The proposed database structure provides several benefits:

- Separates different types of information into logical tables.
- Reduces unnecessary duplication.
- Makes information easier to maintain.
- Uses primary keys to uniquely identify records.
- Uses foreign keys to connect related records.
- Supports data integrity.
- Makes querying and reporting easier.
- Allows social media data to be analysed from different perspectives.
- Supports future expansion of the database.

# Potential Analytical Uses

Once implemented, the database could support analysis such as:

- Most discussed topics.
- Posts with the highest engagement.
- Customer sentiment by topic.
- Number of replies per post.
- Engagement trends over time.
- Users generating the most interactions.
- Topics associated with negative sentiment.
- Frequently mentioned accounts.
- Customer responses to specific posts.

# Skills Demonstrated

- Database Design
- Data Modelling
- Relational Database Concepts
- Primary Keys
- Foreign Keys
- Database Relationships
- Many-to-Many Relationships
- Data Normalisation
- Data Integrity
- Social Media Data Management
- Analytical Data Modelling
- Business Analysis

# Conclusion

This task demonstrated how unstructured social media information can be organised into a structured relational database.

By separating users, posts, replies, quote reposts, mentions, engagement, sentiment, and topics into different tables, the proposed design reduces duplication and makes the information easier to manage and analyse.

Primary keys and foreign keys establish relationships between the tables, while the `Post_Topics` junction table allows posts and topics to have a many-to-many relationship.

The proposed structure provides a foundation for storing Commonwealth Bank social media data and supporting future analysis, reporting, and business decision-making.
