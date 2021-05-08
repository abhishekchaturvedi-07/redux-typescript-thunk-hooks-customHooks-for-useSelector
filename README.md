## Objective - Introducing Typescript with Redux by having a live example. Fetching some input data/package from npm repository/registry and show the details of packages.
 
**Reserve** - *Keyword* -> this is a reserve keyword in Typescript like *for* / *import* etc... So, be aware of using any reserved keyword to avoid any kindof Warnings/Errors!
- We' ve to call and check for package by using word "*repository*" to avoid the issue of ## RESERVE KEYWORDS ##


## What will be inside our REDUX Store here:
**(REDUCER)**
 = repositories-> 
-> data (list of repositories from NPM)
-> loading ( BOOLEAN whether we're fetching data)
-> error ( String, error message if one occured during fetch)

**(ACTION-Creators)**
-> searchRepositories(term/keyword)

**(ACTIONS)**
-> SearchRepositories
-> SearchRepositoriesSuccess
-> SearchRepositoriesError

**(ACTIONS-TYPES)** Create ENUM
-> 'Search_Repositories'
-> 'Search_Repositories_SUCCESS'
-> 'Search_Repositories_ERROR'


**HOW TO INTRODUCE TS IN REDUX**
## APPROACH : (SIMPLIFY STRATEGY)
To have single entry/communication point ie.., one index.ts(which will give access to all other redux stuff to all the other stuff in project) file inside Redux folder and import Reducer/ActionCreator/Middleware in that for a proper folder structure

**Apply TS to Reducer**
1- State type which we are passing to create reducer for that create an interface 
2- Action Type -- TypeGaurd actions (For every action create Interface inside actions folder)
3- Reducer Type, so that the returning action type will be type scripted as per the interface defined


**CUSTOM HOOK**
created custom hook for binding action creators with method : 
## import { bindActionCreators } from 'redux'

**ISSUE ON TYPING AROUND REACT_REDUX**
- this will be seen in useSelector, need to explicitly write a code for defining the state of state paramter . This should be done by react behind the scene only.
## export type RootState = ReturnType<typeof reducers>
//this will returntype ( type of reducers function) and assign it to RootState type
*then create a custom hook for useSelector and export that:*
import {useSelector as _useSelector, TypedUseSelectorHook} from 'react-redux'
import { RootState } from '../redux'
export const useSelector: TypedUseSelectorHook<RootState> = _useSelector# redux-typescript-thunk-hooks-customHooks-for-useSelector
