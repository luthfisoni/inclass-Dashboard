dashboardPage(
    skin = "black",
    dashboardHeader(
        title = "Newton IP"
    ),
    dashboardSidebar(
        sidebarMenu(
            menuItem(
                text = "Personal",
                tabName = "personal",
                badgeLabel = "demographics",
                badgeColor = "red",
                icon = icon("gears")
            ),
            menuItem(
                text = "Billing",
                tabName = "billing",
                badgeLabel = "rate", 
                badgeColor = "green",
                icon = icon("tasks")
            ),
            menuItem(
                text = "Work",
                tabName = "work",
                badgeLabel = "work", 
                badgeColor = "green",
                icon = icon("cubes")
            ),
            menuItem(
                text = "Profile",
                tabName = "profile",
                badgeLabel = "profile", 
                badgeColor = "green",
                icon = icon("user")
            )
        )
        
    ),
    dashboardBody(
        tabItems(
            tabItem(
                tabName = "personal",
                
                fluidRow(
                    box(
                        title = "Overview",
                        width = 12, 
                        
                        radioButtons(inputId = "status", 
                                     label = "Attrition status?", 
                                     choices = unique(data_attrition$attrition), inline = TRUE),
                        
                        valueBoxOutput(
                            outputId = "job_sat", width = 3 
                        ),
                        
                        valueBoxOutput(
                            outputId = "env_sat", width = 3 
                        ),
                        
                        valueBoxOutput(
                            outputId = "tenure", width = 3 
                        ),
                        
                        valueBoxOutput(
                            outputId = "income", width = 3 
                        )
                    ) 
                ),
                fluidRow(
                    box(
                        title = "Numerical Variable",
                        width = 12, 
                        selectInput(inputId = "persnum", 
                                    label = "Select the variable name:", 
                                    selected = "distance_from_home",
                                    choices = data_attrition %>% 
                                        select(age, distance_from_home, 
                                               total_working_years, 
                                               num_companies_worked) %>% 
                                        colnames()),
                        plotlyOutput(outputId = "personalNum")
                    )
                )
            )
        )
    )
)