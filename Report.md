# Milestone 3 Report -- Tracy Wang

## Research Question

**How do voters' perceptions of the economy influence their political preferences in U.S. presidential elections from 2004 to 2020?**

---

## Visualization 1: Income Group and Party Preference Trends Across Time and States

<img src ="..\images\gif\v1_tracy.gif" width="800px">

### Research Task 1: 
**Changes in Party Preferences Across Income Groups Over Time**

#### Objective:
This visualization explores how different income groups supported the Democratic and Republican parties from 2004 to 2020. It also investigates whether this support varies across different states and years. Political analysts and researchers may want to identify if voting preferences are shaped by socioeconomic status, and whether these trends are consistent nationally or vary geographically.

#### Task Description and How This View Supports It:
The dashboard consists of a choropleth map and two bar charts. The map shows the dominant political party in each state and overlays income information using color luminance. The bar charts display how income groups voted in a specific state. By selecting a year and clicking a state, users can explore how income correlates with political alignment over time and geography.

#### Key Features:
- Choropleth map showing dominant party and average income by state.
- Upper bar chart showing vote distribution by party for selected state.
- Lower bar chart showing voter count per income group.
- Year slider and checkbox to toggle color encoding.

#### Visualization Design and Justification:
- **Mark**: area (map), rect (bar charts)
  
| Data Semantics | Channels | Characteristics |
|----------------|----------|-----------------|
| State | Position (Geo Map) | Categorical (spatially meaningful) |
| Dominant Party | Color Hue | Categorical |
| Average Income Level | Opacity / Gradient | Quantitative |
| Vote Counts by Party | Bar Length | Quantitative |
| Income Groups | Color + Bar Length | Categorical + Quantitative |

#### Interaction and Interactivity:
| Interaction | Description | Characteristics |
|-------------|-------------|-----------------|
| Year Slider | Enables comparison across time (2004–2020) | Filter |
| State Click | Updates bar charts to reflect selected state | Filter |
| Checkbox Toggle | Switches between political hue vs grayscale to reduce perceived bias | Selection |
| Tooltip | On hover, displays exact state, income, and party information | Information Display |
| Bar Chart Linking | Selecting a party or income group in one bar chart highlights corresponding elements in the other (bi-directional interaction) | Filter |

#### Critique the view:
This dashboard offers a clear spatial and statistical representation of income-related political trends. However, smaller states are harder to click and interpret on the map. Adding zoom or a list-based state selector could improve accessibility. The opacity encoding may be subtle in some cases; a dual-encoding approach (e.g., color + size) could enhance clarity. Additionally, the bar chart could benefit from sortability or a toggle to switch to percentage view for easier comparison across uneven sample sizes.

---

## Visualization 2: Unemployment Perception and Voting Preference Matrix (State-Linked)

<img src ="..\images\gif\v2_tracy.gif" width="800px">

### Research Task 2: 
**How do voters' perceptions of past and future unemployment shape their party preferences?**

#### Objective:
This visualization investigates how voters' perceptions of past and future unemployment correlate with their political preferences, at both national and state-specific levels. By analyzing how economic optimism or pessimism shapes voting behavior, this view allows political analysts to detect whether those who foresee economic hardship tend to align with a particular political party—and whether this pattern varies across states.

#### Task Description and How This View Supports It:
The chart presents a "Bubble Matrix" where each election year from 2000–2020 is displayed as a row, forming a set of 9 combinations based on past and future unemployment perceptions:
- The X-axis represents perception of past unemployment ("Better", "Same", "Worse").
- The Y-axis represents expectation for future unemployment ("Better", "Same", "Worse").
- The size of each bubble represents the proportion of respondents who support a specific party.
- Color coding is used to distinguish party preference (blue for Democrats, red for Republicans).

#### Key Features:
- Bubble matrix (scatter plots) show the relationship between past/future unemployment perception and party preference, filtered by state (clicked on map).
- Bubbles sized by support percentage for a party and colored by party type.
- Year faceting allows for temporal comparisons.
- Tooltip shows party, perception values, and income group.
- Users can filter specific party information by clicking on one of the bars in the Vote Count in Selected State bar chart, which dynamically updates the bubble matrix.
- Users can filter specific state information by clicking on states in the map, which dynamically updates the bubble matrix.

#### Visualization Design and Justification:
- **Mark**: area (map), point (bubble matrix)
  
| Data Semantics | Channels | Characteristics |
|----------------|----------|-----------------|
| State Location and Attributes | Geoshape, Color | Categorical |
| Past Unemployment Perception | Horizontal Position (X-Axis) | Ordinal (Better, Same, Worse) |
| Future Unemployment Perception | Vertical Position (Y-Axis) | Ordinal (Better, Same, Worse) |
| Vote Preference Percentage | Size (Bubble Radius) | Quantitative |
| Political Party | Color Hue | Categorical |
| Year | Facet Grid (Columns) | Temporal / Categorical |

#### Interaction and Interactivity:
| Interaction | Description | Characteristics |
|-------------|-------------|-----------------|
| State Click | Clicking on a state filters the bubble matrix to show only that state’s data | Filter |
| Hover Tooltip | Shows party support, perception scores, and income group for each bubble | Information Display |
| Party Selection | Clicking a bar in the "Vote Count" chart updates the bubble matrix to display the selected party | Filter |

#### Critique the view:
The grid layout enables straightforward year-over-year comparison and reveals interesting temporal shifts in economic sentiment. However, overlapping bubbles can obscure details in areas of high data density. Adding an interactive zoom feature could allow users to zoom into specific years or data clusters for a closer look at densely packed bubbles. Additionally, displaying multiple years and multidimensional combinations on a single screen can lead to information overload. Consider adding a "year selection" or "animation" feature to make it easier for users to read incrementally.

---

## Visualization 3: Economic Attitudes and Party Alignment Over Time

<img src ="..\images\gif\v3_tracy.gif" width="800px">

### Research Task 3: 
**Shifts in Economic Attitudes and Party Alignment Over Election Cycles**

#### Objective:
This visualization explores how attitudes toward different economic groups—measured via thermometer scores—vary between Democratic and Republican voters, and how these attitudes evolve over time and across states. The goal is to examine ideological divides on economic issues (e.g., business, unions, welfare) and understand whether these divides are consistent nationally or influenced by regional factors.

#### Task Description and How This View Supports It:
The dashboard includes two linked views:
- The top bar chart displays the average thermometer scores by state, filtered by year and economic group.
- The bottom density plot shows the distribution of individual scores by party within a selected state.

When a user selects a state from the bar chart, the density plot updates to show how voters from each party in that state scored a given economic group. This enables exploration of:
- How polarized party attitudes are on different topics.
- Whether Republican and Democratic voters in the same state share similar economic perceptions.
- Changes in sentiment over time, via year-based filters.

#### Key Features:
- Density-based violin plots communicate score distribution and spread.
- Faceted layout by year and economic topic.
- Color hue distinguishes between Democrats and Republicans.
- Tooltips on hover provide exact thermometer ratings.

#### Visualization Design and Justification:
- **Mark**: area (density plot)
  
| Data Semantics | Channels | Characteristics |
|----------------|----------|-----------------|
| Thermometer Score (0–100) | Horizontal Position (X-Axis) | Quantitative |
| Density of Ratings | Vertical Position (Y-Axis) | Quantitative |
| Economic Group (e.g., Business, Welfare) | Filter | Categorical |
| Political Party | Color Hue | Categorical |
| Year | Grid Facet | Temporal |

#### Interaction and Interactivity:
| Interaction | Description | Characteristics |
|-------------|-------------|-----------------|
| State Comparison | Clicking a bar in the "Vote Count" chart updates the density plot to display the selected state's data. | Filter |
| Legend Highlighting | Allows focus on either Democrats or Republicans | Filter |
| Brush Selection | Users select a range of thermometer scores in the bar chart, which updates the density plot to reflect that range of data. | Filter |
| Hover Tooltip | Provides precise values for party, group, and rating distribution | Information Display |

#### Critique the view:
While the density plot effectively visualizes changes in economic attitudes over time, overlap of density curves can obscure the differences between party affiliations, especially in years with similar sentiment. To address this, adjusting the opacity of the curves or using dashed lines for one of the parties could help improve clarity. Additionally, after selecting a score range through the brush interaction, users may find it difficult to reset or clear the selection. Adding a reset button would enhance user experience by allowing them to easily revert back to the full data view and explore new selections seamlessly.
