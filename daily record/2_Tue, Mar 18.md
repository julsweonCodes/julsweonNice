# 2️⃣ Tue, Mar 18

### 📝 To-Do List

- A1 review
    - [x]  Review A1 requirements
    - [x]  A1 peer reviews
    - [ ]  incorporate peer reviews into new class diagram
    - [ ]  incorporate peer reviews into new seq diagrams
- [ ]  Adobe subscription — card info
- A3 meeting (Mar 19) prep
    - [ ]  Go through A3 pdf’s

- A1 review
    
    Review A1 requirements
    
     - initiate pokemon instances each battle
     - manage battle (battle manager)
     - randomness — using seed
     - controlling pokemon’s actions -> defend or attack
     - select next attack or defence skill
     - attack or defend based on currHitPoints/maxHitPoints
     - select attack / defend skill randomly based on seed value (-> seed value)
    
    A1 peer reviews
    
    <aside>
    💡
    
    Readability
    
    - **Cluttered & Disorganized Layout:** Some association lines are too long, making relationships hard to follow.
    - **Variable Naming Issues:** Names like `classMap`, `loadConfig()`, `p1`, and `p2` could be clearer.
    - **Formatting Errors:** UML attributes should follow the "name: Type" format but are inconsistent.
    - **PokemonType Enum Layout:** Listing values horizontally makes them difficult to read.
    </aside>
    
    <aside>
    💡
    
    Validity
    
    - **Misplaced Methods & Responsibilities:**
        - `applyDamage()` and `reduceDamage()` in `AttackSkill` and `DefenseSkill` should **move to the Pokemon class** for better cohesion.
        - `calculateEffectiveDamage()` in `BattleManager` might belong in **Pokemon** instead.
    - **Unnecessary Factory Class:**
        - `PokemonFactory` was criticized as **over-engineered**. Instead of passing `PokemonType`, a **Pokemon name should be passed** to create instances.
    - **Battle Attributes Issue:**
        - `attacker` and `defender` attributes should be **generalized** (e.g., `pokemon1` and `pokemon2`) since they switch roles.
    - **Stack Usage for MovesPerformed:**
        - Keeping track of all previous moves **is unnecessary**—only the last move matters for damage calculation.
    - **Random Class Inconsistency:**
        - The `Random` class appears in some diagrams but is **not consistently integrated**.
    </aside>
    
    <aside>
    💡
    
    Fluidity
    
    - **Extra Information Not in the Problem Statement:**
        - The **PokemonType enum** includes more than required—should have been left **open-ended**.
        - **PokemonFactory may be unnecessary** if Pokémon creation logic can be handled differently.
    - **Class Redundancies:**
        - `DefenseSkill` and `AttackSkill` could be merged into a **single class** with a boolean or type attribute.
    - **Sequence Diagram Inconsistencies:**
        - The **first sequence diagram includes PokemonFactory, but the second does not**, making its role unclear.
    - **Missing Multiplicity in Class Relationships:**
        - The diagram lacks cardinalities (**e.g., how many Skills a Pokémon can have**).
    - **Composition vs Aggregation:**
        - Attack and Defense skills should use **aggregation (empty diamond) instead of composition (filled diamond)** because skills **can be shared across Pokémon**.
    </aside>
    
    <aside>
    💡
    
    Other comments
    
    - **Dashed lines should be used for "uses" dependencies** instead of solid lines.
    - `has` labels on aggregation and composition relationships **are redundant** and should be removed.
    - **Multiplicity should be explicitly stated** (e.g., `1..*`, `0..*`).
    - **Method names in sequence diagrams must match the class diagram** (some methods were missing).
    - **BattleManager and Pokémon instances were labeled as "user" icons instead of objects**.
    
    - Straighten and shorten association lines.
    - Use **better variable names** (avoid `p1`, `p2`, `classMap`).
    - Format attributes correctly (`name: Type`).
    - Move `applyDamage()` and `reduceDamage()` into `Pokemon` instead of `Skill` classes.
    - Consider **removing** `PokemonFactory` or restructuring it.
    - **Merge** `DefenseSkill` and `AttackSkill`.
    - Use **dashed lines for dependencies**.
    - Add **multiplicity** (`1..*`, `0..*`).
    - Fix **composition vs aggregation** (Skills should be aggregation).
    - Ensure **sequence diagrams match class diagrams**.
    - Clarify Battle Flow
        - Change **`attacker/defender`** to `pokemon1/pokemon2`.
        - Store **only the last move instead of an entire move stack**.
    </aside>
    
- A3 meeting prep
    
    <aside>
    💡
    
    Tournament Test Case WalkThrough
    
    ⭐️ Backend
    
    1. Tournament implementation (**must be added to updated diagrams)
    - input: list of pokémon (-> length of pokémon list)
    - output: tournament order
    2. Seed methods — setseed, removeseed
    3. Battle methods — battle(start battle), stop (stop battle)
    
    ⭐️ Command
    
    > battle, Bulbasaur, Pikachu
    
    // battle between Bulbasaur and Pikachu
    
    // Bulbasaur -> Pikachu and rest of the battle is conducted automatically using random numbers until the battle is ended (one pokemon’s hit points reach 0
    
    </aside>