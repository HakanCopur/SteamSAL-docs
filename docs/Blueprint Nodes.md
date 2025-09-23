```cpp
USAL_CreateLeaderboard* USAL_CreateLeaderboard::CreateLeaderboard(const UObject* WorldContextObject,
    const FString& LeaderboardName, ESALLeaderboardSortMethod SortMethod, ESALLeaderboardDisplayType DisplayType)
{
    USAL_CreateLeaderboard* Node = NewObject<USAL_CreateLeaderboard>();
    
    Node->RegisterWithGameInstance(WorldContextObject);
    
    Node->InLeaderboardName = LeaderboardName;
    Node->InSortMethod = SortMethod;
    Node->InDisplayType = DisplayType;
    Node->WorldContextObject = const_cast<UObject*>(WorldContextObject);
    
    return Node;
}
```
